---
title: 'チュートリアル: C++ AMP アプリケーションのデバッグ |Microsoft Docs'
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
ms.openlocfilehash: 3a8c5affeaee73be7dd464ea44ea62db35257f7b
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43689757"
---
# <a name="walkthrough-debugging-a-c-amp-application"></a>チュートリアル : C++ AMP アプリケーションのデバッグ
このトピックでは、グラフィックス処理装置 (GPU) を活用するために C++ Accelerated Massive Parallelism (C++ AMP) を使用するアプリケーションをデバッグする方法を示します。 整数の大きな配列を合計する並列削減プログラムを使用します。 このチュートリアルでは、次の作業について説明します。  
  
- GPU デバッガーを起動しています。  
  
- GPU スレッド] ウィンドウで [GPU スレッドを検査します。  
  
- 使用して、**並列スタック**ウィンドウを同時に複数の GPU スレッドの呼び出し履歴を観察します。  
  
- 使用して、**並列ウォッチ**ウィンドウを同時に複数のスレッドの 1 つの式の値を検査します。  
  
- フラグを設定、フリーズ、凍結解除、および GPU スレッドをグループ化します。  
  
- コードでは、特定の場所にタイルのすべてのスレッドを実行します。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 
このチュートリアルを開始する前に。  
  
- 読み取り[C++ AMP の概要](../../parallel/amp/cpp-amp-overview.md)します。  
  
- その行を確認の数字をテキスト エディターで表示されます。 詳細については、次を参照してください。[方法: エディターで行番号を表示](/visualstudio/ide/reference/how-to-display-line-numbers-in-the-editor)します。  
  
- ソフトウェア エミュレーターでデバッグをサポートするには、Windows 8 または Windows Server 2012 を実行していることを確認します。  
  
 [!INCLUDE[note_settings_general](../../mfc/includes/note_settings_general_md.md)]  
  
### <a name="to-create-the-sample-project"></a>サンプル プロジェクトを作成するには  
  
1. Visual Studio を起動します。  
  
2. メニュー バーで、**[ファイル]**  >  **[新規作成]**  >  **[プロジェクト]** を選択します。  
  
3. [**インストール済み**テンプレート] ペインで選択**Visual C**します。  
  
4. 選択**Win32 コンソール アプリケーション**、型`AMPMapReduce`で、**名前**ボックスを選び、 **OK**ボタン。  
  
5. **[次へ]** ボタンをクリックします。  
  
6. クリア、**プリコンパイル済みヘッダー**チェック ボックスをオンにして、**完了**ボタンをクリックします。  
  
7. **ソリューション エクスプ ローラー**stdafx.h、targetver.h、stdafx.cpp をプロジェクトから削除します。  
  
8. AMPMapReduce.cpp を開き、次のコードでそのコンテンツを置き換えます。  
  
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
  
9. メニュー バーで、**[ファイル]** > **[すべてを保存]** の順に選択します。  
  
10. **ソリューション エクスプ ローラー**、ショートカット メニューを開き**AMPMapReduce**を選び、**プロパティ**します。  
  
11. **プロパティ ページ**ダイアログ ボックスで、**構成プロパティ**、選択**C/C++** > **プリコンパイル済みヘッダー**します。  
  
12. **プリコンパイル済みヘッダーの**プロパティで、**プリコンパイル済みヘッダーを使用しない**、選択し、 **OK**ボタン。  
  
13. メニュー バーで、**[ビルド]** > **[ソリューションのビルド]** の順にクリックします。  
  
## <a name="debugging-the-cpu-code"></a>CPU コードのデバッグ  
 
この手順では、このアプリケーションで CPU コードが正しいことを確認するローカル Windows デバッガーを使用します。 特に興味深いは、このアプリケーションで CPU コードのセグメントは、`for`ループ、`reduction_sum_gpu_kernel`関数。 GPU 上で実行されるツリーに基づく並列リダクションを制御します。  
  
### <a name="to-debug-the-cpu-code"></a>CPU のコードをデバッグするには  
  
1. **ソリューション エクスプ ローラー**、ショートカット メニューを開き**AMPMapReduce**を選び、**プロパティ**します。  
  
2. **プロパティ ページ**ダイアログ ボックスで、**構成プロパティ**、選択**デバッグ**します。 いることを確認**ローカル Windows デバッガー**でが選択されている、**起動するデバッガー**一覧。  
  
3. 戻り、**コード エディター**します。  
  
4. (約 67 行 70 行目) に、次の図に示すコードの行にブレークポイントを設定します。  
  
     ![CPU ブレークポイント](../../parallel/amp/media/campcpubreakpoints.png "campcpubreakpoints")  
CPU ブレークポイント  
  
5. メニュー バーで、**[デバッグ]** > **[デバッグ開始]** の順に選択します。  
  
6. **ローカル**ウィンドウの値を観察`stride_size`70 行目のブレークポイントに達するまでです。  
  
7. メニュー バーで、**[デバッグ]** > **[デバッグの停止]** の順に選択します。  
  
## <a name="debugging-the-gpu-code"></a>GPU コードのデバッグ  
 
このセクションに含まれているコードが GPU コードをデバッグする方法で、`sum_kernel_tiled`関数。 GPU コードでは、並列で「ブロック」ごとに整数の合計を計算します。  
  
### <a name="to-debug-the-gpu-code"></a>GPU コードをデバッグするには  
  
1. **ソリューション エクスプ ローラー**、ショートカット メニューを開き**AMPMapReduce**を選び、**プロパティ**します。  
  
2. **プロパティ ページ**ダイアログ ボックスで、**構成プロパティ**、選択**デバッグ**します。  
  
3. **起動するデバッガー**一覧で、**ローカル Windows デバッガー**します。  
  
4. **デバッガーの種類**一覧で、いることを確認**自動**が選択されています。

    **自動**は既定値です。 Windows 10 では、以前**GPU のみ**の代わりに必要な値は、**自動**します。
  
5. **[OK]** を選択します。  
  
6. 次の図に示すように、30、行にブレークポイントを設定します。  
  
     ![GPU ブレークポイント](../../parallel/amp/media/campgpubreakpoints.png "campgpubreakpoints")  
GPU ブレークポイント  
  
7. メニュー バーで、**[デバッグ]** > **[デバッグ開始]** の順に選択します。 行 67 と 70 行に CPU コード内のブレークポイントは、GPU がこれらのコード行は、CPU 上で実行されるため、デバッグ中には実行されません。  
  
### <a name="to-use-the-gpu-threads-window"></a>GPU スレッド ウィンドウを使用するには  
  
1. 開くには、 **GPU スレッド**ウィンドウ、メニュー バーで、選択**デバッグ** > **Windows** > **GPU スレッド**します。  
  
     GPU スレッドの状態を検査することができます、 **GPU スレッド**ウィンドウが表示されます。  
  
2. ドッキング ステーション、 **GPU スレッド**Visual Studio の下部にあるウィンドウ。 選択、**スレッド スイッチの展開**タイルとスレッドのテキスト ボックスを表示するボタンをクリックします。 **GPU スレッド**ウィンドウでは、次の図に示すように、アクティブでブロックされた GPU スレッドの総数が表示されます。  
  
     ![4 つのアクティブなスレッドでの GPU スレッド ウィンドウ](../../parallel/amp/media/campc.png "campc")  
[GPU スレッド] ウィンドウ  
  
     この計算に割り当てられた 313 のタイルがあります。 各タイルには、32 個のスレッドが含まれています。 ソフトウェア エミュレーターでローカルの GPU デバッグが発生するため、次の 4 つのアクティブな GPU スレッドがあります。 4 つのスレッドの指示を同時に実行し一緒に移動、次の命令。  
  
     **GPU スレッド**ウィンドウで、4 つの GPU スレッドがアクティブと 28 GPU スレッドでブロックされてから、 [tile_barrier::wait](reference/tile-barrier-class.md#wait)について 21 行目で定義されているステートメント (`t_idx.barrier.wait();`)。 最初のタイルに 32 のすべての GPU スレッドが属している`tile[0]`します。 矢印は、現在のスレッドを含む行を指します。 別のスレッドに切り替えると、するには、次のメソッドのいずれかを使用します。  

    - スレッドの内の切り替え先の行で、 **GPU スレッド**ウィンドウで、ショートカット メニューを開き、選択**スレッドに切り替える**します。 行が 1 つ以上のスレッドを表す場合は、スレッド座標に従って最初のスレッドに切り替えることはできます。  
  
    - 対応するテキスト ボックスに、スレッドのタイルとスレッドの値を入力してから、**スイッチ スレッド**ボタンをクリックします。  
  
     **呼び出し履歴**ウィンドウには、現在の GPU スレッドの呼び出し履歴が表示されます。  
  
### <a name="to-use-the-parallel-stacks-window"></a>並列スタック ウィンドウを使用するには  
  
1. 開くには、**並列スタック**ウィンドウ、メニュー バーで、選択**デバッグ** > **Windows** > **並列スタック**.  
  
     使用することができます、**並列スタック**ウィンドウを同時に複数の GPU スレッドのスタック フレームを検査します。  
  
2. ドッキング ステーション、**並列スタック**Visual Studio の下部にあるウィンドウ。  
  
3. 必ず**スレッド**が左上隅にある一覧で選択されています。 次の図に、**並列スタック**ウィンドウで紹介した GPU スレッドのコール スタックに重点を置いたビューが表示されます、 **GPU スレッド**ウィンドウ。  
  
     ![4 つのアクティブ スレッドがある並列スタック ウィンドウ](../../parallel/amp/media/campd.png "campd")  
[並列スタック] ウィンドウ  
  
     32 個のスレッドに問題が発生しました`_kernel_stub`ラムダ ステートメントに、`parallel_for_each`関数呼び出し、続いて、`sum_kernel_tiled`関数の場合、並列リダクションが発生します。 32 個のスレッドから 28 を使用するよう、 [tile_barrier::wait](reference/tile-barrier-class.md#wait)ステートメント、22 行目でブロックされたままに対し、他の 4 つのスレッドでアクティブのままにし、 `sum_kernel_tiled` 30 行での関数。  

     使用可能な GPU スレッドのプロパティを検査することができます、 **GPU スレッド**ウィンドウの豊富なデータヒントで、**並列スタック**ウィンドウ。 これを行うには、スタック フレームにマウス ポインターを置く**sum_kernel_tiled**します。 次の図は、データヒントを示します。  
  
     ![並列スタック ウィンドウのデータヒント](../../parallel/amp/media/campe.png "campe")  
GPU スレッド データヒント  
  
     詳細については、**並列スタック**ウィンドウを参照してください[並列スタック ウィンドウを使用して](/visualstudio/debugger/using-the-parallel-stacks-window)します。  
  
### <a name="to-use-the-parallel-watch-window"></a>並列ウォッチ ウィンドウを使用するには  
  
1. 開くには、**並列ウォッチ**ウィンドウ、メニュー バーで、選択**デバッグ** > **Windows** > **並列ウォッチ**  > **並列ウォッチ 1**します。  
  
     使用することができます、**並列ウォッチ**ウィンドウを複数のスレッド間で式の値を検査します。  
  
2. ドッキング ステーション、 **並列ウォッチ 1** Visual Studio の一番下のウィンドウ。 32 行のテーブルには、**並列ウォッチ**ウィンドウ。 GPU スレッド ウィンドウに表示された GPU スレッドに対応し、**並列スタック**ウィンドウ。 ここで、すべての 32 GPU スレッド間で検査する値を持つ式を入力できます。  
  
3. 選択、**ウォッチ式の追加**列ヘッダーを入力`localIdx`、選択し、 **」と入力**キー。  
  
4. 選択、**ウォッチ式の追加**列ヘッダーをもう一度、型`globalIdx`を選択し、 **」と入力**キー。  
  
5. 選択、**ウォッチ式の追加**列ヘッダーをもう一度、型`localA[localIdx[0]]`を選択し、 **」と入力**キー。  
  
     指定された式では、対応する列のヘッダーを選択して並べ替えることができます。  
  
     選択、 **localA [localIdx [0]** 列の並べ替えに列ヘッダー。 次の図での並べ替えの結果**localA [localIdx [0]** します。  
  
     ![並列ウォッチ ウィンドウの並べ替えられた結果](../../parallel/amp/media/campf.png "campf")  
 並べ替えの結果  
  
     コンテンツをエクスポートすることができます、**並列ウォッチ**を選択して excel ウィンドウ、 **Excel**ボタンをクリックし、 **Excel で開く**します。 開発用コンピューターに Excel をインストールした場合、コンテンツを含む Excel ワークシートが開きます。  
  
6. 右上隅にある、**並列ウォッチ**ウィンドウで、ブール式を使用して、コンテンツをフィルター処理に使用できるフィルター コントロールが用意されています。 Enter`localA[localIdx[0]] > 20000`フィルター コントロールのテキスト ボックスをクリックして、 **Enter**キー。  
  
     ウィンドウにスレッドのみが含まれています、`localA[localIdx[0]]`値は 20000 を超える。 コンテンツは、並べ替えられた、`localA[localIdx[0]]`列は、以前に実行する並べ替え操作です。  
  
## <a name="flagging-gpu-threads"></a>GPU スレッドに対するフラグの設定  
 
特定の GPU スレッドをマークするにはフラグを設定して、 **GPU スレッド**ウィンドウで、**並列ウォッチ**ウィンドウ、または、データヒントで、**並列スタック**ウィンドウ。 GPU スレッド ウィンドウ内の行に 1 つ以上のスレッドが含まれている場合は、行に含まれているすべてのスレッドにフラグその行に対するフラグの設定です。  
  
### <a name="to-flag-gpu-threads"></a>GPU スレッドにフラグを  
  
1. 選択、 **[スレッド]** 内の列ヘッダー、 **並列ウォッチ 1**タイル インデックスとスレッドのインデックスを並べ替えるにはウィンドウ。  
  
2. メニュー バーで、**デバッグ** > **続行**、進行状況を (AMPMapReduce.cpp の 32 行目で定義されている) [次へ] のバリアにアクティブだった 4 つのスレッドを停止します。  
  
3. 今すぐアクティブになっている 4 つのスレッドを含む行の左側にあるフラグ シンボルを選択します。  
  
     次の図は、4 つのアクティブなフラグが設定されたスレッド、 **GPU スレッド**ウィンドウ。  
  
     ![フラグが設定されたスレッドでの GPU スレッド ウィンドウ](../../parallel/amp/media/campg.png "campg")  
[GPU スレッド] ウィンドウのアクティブなスレッド  
  
     **並列ウォッチ**ウィンドウとのデータヒント、**並列スタック**両方のウィンドウでフラグが設定されたスレッドを示します。  
  
4. フラグを設定した 4 つのスレッドに集中する場合でを表示することができます、 **GPU スレッド**、**並列ウォッチ**、および**並列スタック**windows でのみフラグスレッド。  
  
     選択、**のみのフラグが設定を表示する**ボタンのいずれかを windows のか、**デバッグの場所**ツールバー。 次の図は、**のみのフラグが設定を表示する**のボタンでは、**デバッグの場所**ツールバー。  
  
     ![デバッグの場所 ツールバーのアイコンの表示のみにフラグが設定された](../../parallel/amp/media/camph.png "camph")  
**フラグが設定のみを表示する**ボタン  
  
     今すぐ、 **GPU スレッド**、**並列ウォッチ**と**並列スタック**windows フラグが設定されたスレッドのみを表示します。  
  
## <a name="freezing-and-thawing-gpu-threads"></a>GPU スレッドの凍結と凍結解除  
 
固定することができます (中断) し、いずれかから (再開) GPU スレッドの凍結解除、 **GPU スレッド**ウィンドウまたは**並列ウォッチ**ウィンドウ。 凍結して同じ方法で CPU スレッドを凍結解除については、次を参照してください。[方法: [スレッド] ウィンドウを使用して、](/visualstudio/debugger/how-to-use-the-threads-window)します。  
  
### <a name="to-freeze-and-thaw-gpu-threads"></a>凍結し、GPU スレッドを凍結解除  
  
1. 選択、**のみのフラグが設定を表示する**のすべてのスレッドを表示するボタンをクリックします。  
  
2. メニュー バーで、**デバッグ** > **続行**します。  
  
3. アクティブな行のショートカット メニューを開き、選択し、**固定**します。  
  
     次の図の**GPU スレッド**4 つのすべてのスレッドが固定されているウィンドウに表示されます。  
  
     ![GPU スレッド ウィンドウの凍結されたスレッドを示す](../../parallel/amp/media/campk.png "campk")  
スレッドを凍結、 **GPU スレッド**ウィンドウ  
  
     同様に、**並列ウォッチ**4 つのすべてのスレッドが固定されているウィンドウに表示されます。  
  
4. メニュー バーで、**デバッグ** > **続行**次の 4 つの GPU スレッドがバリア 22 行目で進行状況を 30 行のブレークポイントに到達することができるようにします。 **GPU スレッド**ウィンドウが固定されたとアクティブな状態で保持されていたの 4 つのスレッドが残ることを示します。  
  
5. メニュー バーで、**デバッグ**、**続行**します。  
  
6. **並列ウォッチ**ウィンドウで、個人または複数の GPU スレッド凍結解除できることもできます。  
  
### <a name="to-group-gpu-threads"></a>GPU スレッドをグループ化  
  
1. 内のスレッドのいずれかのショートカット メニューで、 **GPU スレッド**ウィンドウで、選択**Group By**、**アドレス**します。  
  
     内のスレッド、 **GPU スレッド**ウィンドウは、アドレスによってグループ化されます。 アドレスは、逆アセンブル時のスレッドの各グループが配置される命令に対応します。 24 のスレッドは 22 行目で、場所、 [tile_barrier::wait メソッド](reference/tile-barrier-class.md#wait)を実行します。 12 個のスレッドは、行 32 バリアの命令では。 これらのスレッドの 4 つはフラグが設定されます。 8 個のスレッドは、30 行のブレークポイントでは。 これらのスレッドの 4 つが固定されています。 次の図は、グループ化されたスレッド、 **GPU スレッド**ウィンドウ。  

     ![GPU スレッド ウィンドウのスレッドがアドレスでグループ化された](../../parallel/amp/media/campl.png "campl")  
内のスレッドをグループ化、 **GPU スレッド**ウィンドウ  
  
2. 実行することも、 **Group By**操作のデータ グリッドのショートカット メニューを開き、**並列ウォッチ**ウィンドウで、選択**Group By**メニューを選択しスレッドをグループ化する方法に対応する項目。  
  
## <a name="running-all-threads-to-a-specific-location-in-code"></a>コード内の特定の場所にすべてのスレッドを実行しています。  
 
特定のタイルを使用して、カーソルを含む行にすべてのスレッドを実行する**現在タイル カーソルまで実行**します。  
  
### <a name="to-run-all-threads-to-the-location-marked-by-the-cursor"></a>カーソルがマークされている場所へのすべてのスレッドを実行するには  
  
1. 凍結されたスレッドのショートカット メニューで**凍結解除**します。  
  
2. **コード エディター**30 行にカーソルを置きます。  
  
3. ショートカット メニューで、**コード エディター**、選択**カーソルを現在のタイルを実行**します。  
  
     21 行目にあるバリアでブロックされていた以前 24 のスレッドが 32 の行に進行します。 これに示した、 **GPU スレッド**ウィンドウ。  
  
## <a name="see-also"></a>関連項目  
 
[C++ AMP の概要](../../parallel/amp/cpp-amp-overview.md)   
[GPU コードのデバッグ](/visualstudio/debugger/debugging-gpu-code)   
[方法: GPU スレッド ウィンドウを使用](/visualstudio/debugger/how-to-use-the-gpu-threads-window)   
[方法: 並列ウォッチ ウィンドウの使用](/visualstudio/debugger/how-to-use-the-parallel-watch-window)   
[同時実行ビジュアライザーで C++ AMP コードの分析](https://blogs.msdn.microsoft.com/nativeconcurrency/2012/03/09/analyzing-c-amp-code-with-the-concurrency-visualizer/)