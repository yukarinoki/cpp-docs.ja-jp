---
title: 'チュートリアル: C++ AMP アプリケーションのデバッグ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- debugging, C++ Accelerated Massive Parallelism
- C++ AMP, debugging
- C++ Accelerated Massive Parallelism, debugging
- debugging, C++ AMP
ms.assetid: 40e92ecc-f6ba-411c-960c-b3047b854fb5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1bf80276b5434804651bcc4507397e9479f6e494
ms.sourcegitcommit: da7b7533d1a4dc141cc0f09149e4e4196f2fe329
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2018
---
# <a name="walkthrough-debugging-a-c-amp-application"></a>チュートリアル : C++ AMP アプリケーションのデバッグ
このトピックでは、C++ Accelerated Massive Parallelism (C++ AMP) を使用して、グラフィックス処理装置 (GPU) を利用するアプリケーションをデバッグする方法を示します。 整数の大きな配列を合計する並列リダクション プログラムを使用します。 このチュートリアルでは、次の作業について説明します。  
  
-   GPU デバッガーを起動しています。  
  
-   [GPU スレッド] ウィンドウの GPU スレッドを検査します。  
  
-   並列スタック ウィンドウを使用して、同時に複数の GPU スレッドの呼び出し履歴を確認します。  
  
-   並列ウォッチ ウィンドウを使用して、複数のスレッドで同時に 1 つの式の値を確認します。  
  
-   フラグを設定する、固定、凍結解除、および GPU スレッドをグループ化します。  
  
-   コード内の特定の場所のタイルのすべてのスレッドを実行します。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 このチュートリアルを開始する前に。  
  
-   読み取り[C++ AMP の概要](../../parallel/amp/cpp-amp-overview.md)です。  
  
-   その行を確認番号が、テキスト エディターに表示されます。 詳細については、次を参照してください。[する方法: エディターで行番号の表示](/visualstudio/ide/reference/how-to-display-line-numbers-in-the-editor)です。  
  
-   実行しているかどうかを確認[!INCLUDE[win8](../../build/reference/includes/win8_md.md)]または[!INCLUDE[winserver8](../../build/reference/includes/winserver8_md.md)]ソフトウェア エミュレーターでデバッグをサポートします。  
  
 [!INCLUDE[note_settings_general](../../mfc/includes/note_settings_general_md.md)]  
  
### <a name="to-create-the-sample-project"></a>サンプル プロジェクトを作成するには  
  
1.  Visual Studio を起動します。  
  
2.  メニュー バーで、 **[ファイル]**、 **[新規作成]**、 **[プロジェクト]** の順にクリックします。  
  
3.  [**インストール**テンプレート] ペインで選択**Visual C**です。  
  
4.  選択**Win32 コンソール アプリケーション**、型`AMPMapReduce`で、**名前**ボックスをクリックして、 **[ok]** ボタンをクリックします。  
  
5.  **[次へ]** ボタンをクリックします。  
  
6.  クリア、**プリコンパイル済みヘッダー**チェック ボックスをオンにして、**完了**ボタンをクリックします。  
  
7.  **ソリューション エクスプ ローラー**stdafx.h、targetver.h、および stdafx.cpp をプロジェクトから削除します。  
  
8.  AMPMapReduce.cpp を開き、次のコードでそのコンテンツを置き換えます。  
  
 ```cpp  
    // AMPMapReduce.cpp defines the entry point for the program.  
    // The program performs a parallel-sum reduction that computes the sum of an array of integers.   
  
    #include <stdio.h>  
    #include <tchar.h>  
    #include <amp.h>  
  
    const int BLOCK_DIM = 32;  
  
    using namespace concurrency;  
  
    void sum_kernel_tiled(tiled_index<BLOCK_DIM> t_idx, array<int, 1> &A, int stride_size) restrict(amp)  
    {  
        tile_static int localA[BLOCK_DIM];  
  
        index<1> globalIdx = t_idx.global * stride_size;  
        index<1> localIdx = t_idx.local;  
  
        localA[localIdx[0]] =  A[globalIdx];  
  
        t_idx.barrier.wait();  
  
        // Aggregate all elements in one tile into the first element.  
        for (int i = BLOCK_DIM / 2; i > 0; i /= 2)   
        {  
            if (localIdx[0] < i)   
            {  
  
                localA[localIdx[0]] += localA[localIdx[0] + i];  
            }  
  
            t_idx.barrier.wait();  
        }  
  
        if (localIdx[0] == 0)  
        {  
            A[globalIdx] = localA[0];  
        }  
    }  
  
    int size_after_padding(int n)  
    {  
        // The extent might have to be slightly bigger than num_stride to   
        // be evenly divisible by BLOCK_DIM. You can do this by padding with zeros.  
        // The calculation to do this is BLOCK_DIM * ceil(n / BLOCK_DIM)  
        return ((n - 1) / BLOCK_DIM + 1) * BLOCK_DIM;  
    }  
  
    int reduction_sum_gpu_kernel(array<int, 1> input)   
    {  
        int len = input.extent[0];  
  
        //Tree-based reduction control that uses the CPU.  
        for (int stride_size = 1; stride_size < len; stride_size *= BLOCK_DIM)   
        {  
            // Number of useful values in the array, given the current  
            // stride size.  
            int num_strides = len / stride_size;    
  
            extent<1> e(size_after_padding(num_strides));  
  
            // The sum kernel that uses the GPU.  
            parallel_for_each(extent<1>(e).tile<BLOCK_DIM>(), [&input, stride_size] (tiled_index<BLOCK_DIM> idx) restrict(amp)  
            {  
                sum_kernel_tiled(idx, input, stride_size);  
            });  
        }  
  
        array_view<int, 1> output = input.section(extent<1>(1));  
        return output[0];  
    }  
  
    int cpu_sum(const std::vector<int> &arr) {  
        int sum = 0;  
        for (size_t i = 0; i < arr.size(); i++) {  
            sum += arr[i];  
        }  
        return sum;  
    }  
  
    std::vector<int> rand_vector(unsigned int size) {  
        srand(2011);  
  
        std::vector<int> vec(size);  
        for (size_t i = 0; i < size; i++) {  
            vec[i] = rand();  
        }  
        return vec;  
    }  
  
    array<int, 1> vector_to_array(const std::vector<int> &vec) {  
        array<int, 1> arr(vec.size());  
        copy(vec.begin(), vec.end(), arr);  
        return arr;  
    }  
  
    int _tmain(int argc, _TCHAR* argv[])  
    {  
        std::vector<int> vec = rand_vector(10000);  
        array<int, 1> arr = vector_to_array(vec);  
  
        int expected = cpu_sum(vec);  
        int actual = reduction_sum_gpu_kernel(arr);  
  
        bool passed = (expected == actual);  
        if (!passed) {  
            printf("Actual (GPU): %d, Expected (CPU): %d", actual, expected);  
        }  
        printf("sum: %s\n", passed  "Passed!" : "Failed!");   
  
        getchar();  
  
        return 0;  
    }  
  
 ```  
  
9. メニュー バーで、**[ファイル]**、**[すべてを保存]** の順に選択します。  
  
10. **ソリューション エクスプ ローラー**、ショートカット メニューを開き、 **AMPMapReduce**を選択し**プロパティ**です。  
  
11. **プロパティ ページ**ダイアログ ボックスで、**構成プロパティ**、選択**C/C++**、**プリコンパイル済みヘッダー**です。  
  
12. **プリコンパイル済みヘッダーの**プロパティを選択**プリコンパイル済みヘッダーを使用しない**を選択し、 **OK**ボタンをクリックします。  
  
13. メニュー バーの **[ビルド]**、 **[ソリューションのビルド]** の順にクリックします。  
  
## <a name="debugging-the-cpu-code"></a>CPU コードのデバッグ  
 この手順では、ローカル Windows デバッガーを使用してこのアプリケーションの CPU コードが正しいことを確認します。 特に興味深いは、このアプリケーションでの CPU コードのセグメントは、`for`ループ、`reduction_sum_gpu_kernel`関数。 GPU 上で実行されるツリーに基づく並列リダクションを制御します。  
  
### <a name="to-debug-the-cpu-code"></a>CPU コードをデバッグするには  
  
1.  **ソリューション エクスプ ローラー**、ショートカット メニューを開き、 **AMPMapReduce**を選択し**プロパティ**です。  
  
2.  **プロパティ ページ**ダイアログ ボックスで、**構成プロパティ**、選択**デバッグ**です。 いることを確認**ローカル Windows デバッガー**でが選択されている、**起動するデバッガー**  ボックスの一覧です。  
  
3.  コード エディターに戻る  
  
4.  (約は複数の行 67 行 70) の次の図に示すようにコードの行にブレークポイントを設定します。  
  
     ![CPU ブレークポイント](../../parallel/amp/media/campcpubreakpoints.png "campcpubreakpoints")  
CPU ブレークポイント  
  
5.  メニュー バーで、**[デバッグ]**、**[デバッグ開始]** の順に選択します。  
  
6.  **ローカル**ウィンドウの値を観察`stride_size`70 の行のブレークポイントに到達するまでです。  
  
7.  メニュー バーで、**[デバッグ]**、**[デバッグの停止]** の順に選択します。  
  
## <a name="debugging-the-gpu-code"></a>GPU コードのデバッグ  
 このセクションの内容が含まれているコードは、GPU のコードをデバッグする方法を示しますで、`sum_kernel_tiled`関数。 GPU コードは、「ブロック」ごとに整数の合計を並列で計算します。  
  
### <a name="to-debug-the-gpu-code"></a>GPU コードをデバッグするには  
  
1.  **ソリューション エクスプ ローラー**、ショートカット メニューを開き、 **AMPMapReduce**を選択し**プロパティ**です。  
  
2.  **プロパティ ページ**ダイアログ ボックスで、**構成プロパティ**、選択**デバッグ**です。  
  
3.  **起動するデバッガー**一覧で、**ローカル Windows デバッガー**です。  
  
4.  **デバッガーの種類**ボックスの一覧であることを確認**自動**が選択されています。

    **自動**既定値です。 Windows 10 より前**GPU のみ**の代わりに必要な値は、**自動**です。
  
5.  **[OK]** を選択します。  
  
6.  次の図に示すように、30 の行にブレークポイントを設定します。  
  
     ![GPU ブレークポイント](../../parallel/amp/media/campgpubreakpoints.png "campgpubreakpoints")  
GPU ブレークポイント  
  
7.  メニュー バーで、**[デバッグ]**、**[デバッグ開始]** の順に選択します。 コードでは、CPU、67 および 70 行のブレークポイントは、GPU がこれらのコード行は、CPU 上で実行されるため、デバッグ中には実行されません。  
  
### <a name="to-use-the-gpu-threads-window"></a>GPU スレッド ウィンドウを使用するには  
  
1.  開くには、GPU スレッド ウィンドウ、メニュー バーで、次のように選択します。**デバッグ**、 **Windows**、 **GPU スレッド**です。  
  
     GPU スレッドに表示される [GPU スレッド] ウィンドウで状態を検査することができます。  
  
2.  Visual Studio の下部にある [GPU スレッド] ウィンドウをドッキングします。 選択、**スレッド スイッチの拡張**タイルとスレッドのテキスト ボックスを表示するボタンをクリックします。 GPU スレッド ウィンドウは、次の図に示すように、アクティブおよびブロックの GPU スレッドの合計数を示します。  
  
     ![GPU スレッド ウィンドウで 4 個のアクティブなスレッド](../../parallel/amp/media/campc.png "campc")  
[GPU スレッド] ウィンドウ  
  
     この計算に割り当てられた 313 のタイルがあります。 各タイルには、32 個のスレッドが含まれています。 ソフトウェア エミュレーターでローカルの GPU デバッグが発生するため、次の 4 つのアクティブな GPU スレッド。 4 つのスレッドの指示を同時に実行し、移動一緒に次の命令。  
  
     GPU スレッド ウィンドウで次の 4 つ GPU スレッドがアクティブなとで 28 GPU スレッドがブロックされている、 [tile_barrier::wait](reference/tile-barrier-class.md#wait)に関する 21 行目で定義されているステートメント (`t_idx.barrier.wait();`)。 最初のタイルに属しているすべての 32 個の GPU スレッド`tile[0]`です。 矢印は、現在のスレッドを含む行を指します。 別のスレッドに切り替えると、するには、次のいずれかを使用します。  

  
    -   [GPU スレッド] ウィンドウに切り替えるには、スレッドの行で、ショートカット メニューを開き**スレッドに切り替える**です。 行が複数のスレッドである場合は、スレッド座標に従って最初のスレッドに切り替わります。  
  
    -   対応するテキスト ボックス内のスレッドのタイルとスレッドの値を入力し、、**スイッチ スレッド**ボタンをクリックします。  
  
     呼び出し履歴 ウィンドウでは、現在の GPU スレッドの呼び出し履歴を表示します。  
  
### <a name="to-use-the-parallel-stacks-window"></a>並列スタック ウィンドウを使用するには  
  
1.  開くには、並列スタック ウィンドウ、メニュー バーで、次のように選択します。**デバッグ**、 **Windows**、**並列スタック**です。  
  
     並列スタック ウィンドウを使用すると、同時に複数の GPU スレッドのスタック フレームを検査します。  
  
2.  Visual Studio の下部にある [並列スタック] ウィンドウをドッキングします。  
  
3.  確認して**スレッド**が左上隅にある一覧で選択されています。 次の図では、並列スタック ウィンドウは、GPU スレッド ウィンドウが表示される GPU スレッドのコール スタックのフォーカスされたビューを示します。  
  
     ![4 個のアクティブなスレッドを使用する並列スタック ウィンドウ](../../parallel/amp/media/campd.png "campd")  
[並列スタック] ウィンドウ  
  
     32 個のスレッドになりました`_kernel_stub`ラムダのステートメントに、`parallel_for_each`関数呼び出しとし、さらに、`sum_kernel_tiled`関数の場合、並列リダクションが発生します。 32 個のスレッドから 28 に進み、 [tile_barrier::wait](reference/tile-barrier-class.md#wait)ステートメント行 22、ブロックされたままに対し、他の 4 個のスレッドでアクティブのままにし、`sum_kernel_tiled`行 30 の関数。  

  
     並列スタック ウィンドウの機能豊富なデータヒント に GPU スレッド ウィンドウで使用可能な GPU スレッドのプロパティを検査することができます。 これを行うには、スタック フレームにマウス ポインターを置く**sum_kernel_tiled**です。 次の図は、データヒントを示します。  
  
     ![並列スタック ウィンドウのデータヒント](../../parallel/amp/media/campe.png "campe")  
GPU スレッド データヒント  
  
     [並列スタック ウィンドウの詳細については、次を参照してください。[並列スタック] ウィンドウを使用して](/visualstudio/debugger/using-the-parallel-stacks-window)です。  
  
### <a name="to-use-the-parallel-watch-window"></a>並列ウォッチ ウィンドウを使用するには  
  
1.  開くには、並列ウォッチ ウィンドウ、メニュー バーで、次のように選択します。**デバッグ**、 **Windows**、**並列ウォッチ**、**並列ウォッチ 1**です。  
  
     並列ウォッチ ウィンドウを使用すると、複数のスレッドで式の値を確認します。  
  
2.  [並列ウォッチ 1] ウィンドウを Visual Studio の下部にドッキングします。 並列ウォッチ ウィンドウのテーブルでは、32 の行があります。 GPU スレッド ウィンドウと並列スタック ウィンドウの両方に表示されていた GPU スレッドにそれぞれ対応します。 ここで、すべての 32 GPU スレッド間で検査する値を持つ式を入力できます。  
  
3.  選択、**ウォッチ式の追加**列ヘッダーを入力`localIdx`、し、Enter キーを押します。  
  
4.  選択、**ウォッチ式の追加**列ヘッダーをもう一度、型`globalIdx`、し、Enter キーを押します。  
  
5.  選択、**ウォッチ式の追加**列ヘッダーをもう一度、型`localA[localIdx[0]]`、し、Enter キーを押します。  
  
     指定された式で並べ替えるには、対応する列のヘッダーを選択します。  
  
     選択、 **localA [localIdx [0]** 列見出し、列の並べ替えにします。 次の図での並べ替えの結果**localA [localIdx [0]** です。  
  
     ![結果が並べ替えられて並列ウォッチ ウィンドウ](../../parallel/amp/media/campf.png "campf")  
 並べ替えの結果  
  
     並列ウォッチ ウィンドウの内容を Excel にエクスポートするには、Excel ボタンを選択し、 **Excel で開く**です。 開発用コンピューターに Excel をインストールした場合、コンテンツを含む Excel ワークシートが開きます。  
  
6.  並列ウォッチ] ウィンドウの右上隅にある [ブール式を使用してコンテンツをフィルター処理に使用できるフィルター コントロールがあります。 Enter`localA[localIdx[0]] > 20000`フィルター コントロールのテキスト ボックスし、Enter キーを押します。  
  
     ウィンドウにいるスレッドのみが含まれています、`localA[localIdx[0]]`値 20000 を超えています。 コンテンツに引き続き並べ替えて、`localA[localIdx[0]]`列で、並べ替えの動作が以前に実行します。  
  
## <a name="flagging-gpu-threads"></a>GPU スレッドに対するフラグの設定  
 特定の GPU スレッドをマークするには、GPU スレッド ウィンドウ、並列ウォッチ ウィンドウで、または並列スタック ウィンドウのデータヒントでそのフラグを設定します。 GPU スレッド ウィンドウ内の行に複数のスレッドが含まれている場合は、行に含まれているすべてのスレッドにフラグの該当する行のフラグを設定します。  
  
### <a name="to-flag-gpu-threads"></a>GPU スレッドにフラグを設定するには  
  
1.  選択、 **[スレッド]** タイル インデックスとスレッドのインデックスを並べ替えるには [並列ウォッチ 1] ウィンドウで列のヘッダー。  
  
2.  メニュー バーで、次のように選択します。**デバッグ**、**続行**、進行状況を (AMPMapReduce.cpp の 32 行目で定義されている)、[次へ] のバリアにアクティブだった 4 つのスレッドを停止します。  
  
3.  今すぐアクティブになっている 4 つのスレッドが含まれる行の左側にあるフラグ シンボルを選択します。  
  
     次の図は、[GPU スレッド] ウィンドウの 4 つのアクティブなフラグが設定されたスレッドを示します。  
  
     ![GPU スレッド ウィンドウでフラグが設定されたスレッド](../../parallel/amp/media/campg.png "campg")  
[GPU スレッド] ウィンドウのアクティブなスレッド  
  
     並列ウォッチ ウィンドウと並列スタック ウィンドウの両方のデータヒントは、フラグが設定されたスレッドを示しています。  
  
4.  フラグを設定した 4 つのスレッドに重点を置く場合は、表示するには、GPU スレッド、並列ウォッチ] と [並列スタック ウィンドウでフラグが設定されたスレッドのみ選択できます。  
  
     ボタンをクリックしてのみフラグが設定を表示するいずれかで、windows のまたは、**デバッグの場所**ツールバー。 次の図にのみフラグが設定を表示するボタンを示しています、**デバッグの場所**ツールバー。  
  
     ![デバッグの場所 ツールバーのアイコンが表示のみにフラグが設定された](../../parallel/amp/media/camph.png "camph")  
[フラグが設定されているスレッドのみを表示] ボタン  
  
     これで、GPU スレッド、並列ウォッチ ウィンドウと並列スタック ウィンドウは、フラグが設定されたスレッドのみを表示します。  
  
## <a name="freezing-and-thawing-gpu-threads"></a>GPU スレッドを凍結と凍結解除  
 固定することができます (中断) および GPU スレッド ウィンドウまたは 並列ウォッチ ウィンドウから (再開) GPU スレッドを凍結解除します。 凍結して同じ方法で CPU スレッドを凍結解除詳細については、次を参照してください。[する方法: [スレッド] ウィンドウを使用して](/visualstudio/debugger/how-to-use-the-threads-window)です。  
  
### <a name="to-freeze-and-thaw-gpu-threads"></a>GPU スレッドを凍結解除したり凍結解除したりする  
  
1.  選択、**フラグが設定のみを表示**すべてのスレッドを表示するボタンをクリックします。  
  
2.  メニュー バーで、次のように選択します。**デバッグ**、**続行**です。  
  
3.  アクティブな行のショートカット メニューを開き、選択**凍結**です。  
  
     GPU スレッド ウィンドウの次の図は、次の 4 つのすべてのスレッドが固定されていることを示します。  
  
     ![GPU スレッド ウィンドウの凍結されたスレッドを示す](../../parallel/amp/media/campk.png "campk")  
[GPU スレッド] ウィンドウの凍結されたスレッド  
  
     同様に、並列ウォッチ ウィンドウでは、次の 4 つのすべてのスレッドが固定されていることを示しています。  
  
4.  メニュー バーで、次のように選択します。**デバッグ**、**続行**30 の行にブレークポイントに到達すると過去のバリア 22 行目に進行状況を次の 4 つの GPU スレッドを許可します。 GPU スレッド ウィンドウは、固定されていると、アクティブな状態で保持されていたの 4 つのスレッドが残ることを示します。  
  
5.  メニュー バーで、次のように選択します。**デバッグ**、**続行**です。  
  
6.  並列ウォッチ ウィンドウからは、個人または複数の GPU スレッドも解除ことができます。  
  
### <a name="to-group-gpu-threads"></a>GPU スレッドをグループ化  
  
1.  内のスレッドの 1 つのショートカット メニューで、 **GPU スレッド**ウィンドウで、選択**Group By**、**アドレス**です。  
  
     GPU スレッド ウィンドウ内のスレッドは、アドレスでグループ化されます。 アドレスは、スレッドの各グループがあるの逆アセンブリ内の命令に対応しています。 24 のスレッドは、22 の行で、場所、 [tile_barrier::wait メソッド](reference/tile-barrier-class.md#wait)を実行します。 12 個のスレッドは、32 の行で、バリアの命令でです。 これらのスレッドのうち 4 つはフラグが付けられます。 8 個のスレッドは、30 の行のブレークポイントでです。 これらのスレッドのうち 4 つに固定されます。 次の図は、GPU スレッド ウィンドウでグループ化されたスレッドを示します。  

  
     ![GPU スレッド ウィンドウは、アドレスでグループ化された](../../parallel/amp/media/campl.png "campl")  
GPU スレッド ウィンドウでグループ化されたスレッド  
  
2.  実行することも、 **Group By**並列ウォッチ ウィンドウのデータ グリッドのショートカット メニューを開き操作を選択する**Group By**、希望の方法に対応するメニュー項目を選択し、スレッドをグループ化します。  
  
## <a name="running-all-threads-to-a-specific-location-in-code"></a>コード内の特定の場所にすべてのスレッドを実行しています。  
 使用して、カーソルを含む行に指定されたタイルのすべてのスレッドを実行する**現在タイル カーソルまで実行**です。  
  
### <a name="to-run-all-threads-to-the-location-marked-by-the-cursor"></a>カーソルで示される場所にすべてのスレッドを実行するには  
  
1.  凍結されたスレッドのショートカット メニューで**凍結解除**です。  
  
2.  コード エディターでは、30 の行にカーソルを置きます。  
  
3.  コード エディターのショートカット メニューで選択**カーソルを現在のタイルを実行**です。  
  
     21 行目にあるバリアでブロックされていた 24 のスレッドが 32 の行になるまでの進行します。 これに示されて、 **GPU スレッド**ウィンドウです。  
  
## <a name="see-also"></a>関連項目  
 [C++ AMP の概要](../../parallel/amp/cpp-amp-overview.md)   
 [GPU コードのデバッグ](/visualstudio/debugger/debugging-gpu-code)   
 [方法: GPU スレッド ウィンドウを使用します。](/visualstudio/debugger/how-to-use-the-gpu-threads-window)   
 [方法: 並列ウォッチ ウィンドウの使用](/visualstudio/debugger/how-to-use-the-parallel-watch-window)   
 [同時実行ビジュアライザーで C++ AMP コードを分析します。](http://go.microsoft.com/fwlink/p/?linkid=253987&clcid=0x409)

