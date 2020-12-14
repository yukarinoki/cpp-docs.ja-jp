---
description: '詳細については、「チュートリアル: 行列乗算」を参照してください。'
title: 'チュートリアル : 行列乗算'
ms.date: 04/23/2019
ms.assetid: 61172e8b-da71-4200-a462-ff3a908ab0cf
ms.openlocfilehash: 8be1964d047d0fe075d652d94f53112c5e1b267f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222217"
---
# <a name="walkthrough-matrix-multiplication"></a>チュートリアル : 行列乗算

このチュートリアルでは、C++ AMP を使用して行列乗算の実行を高速化する方法を示します。 タイルを使用する場合と使用しない場合の 2 つのアルゴリズムを紹介します。

## <a name="prerequisites"></a>前提条件

開始する前に次の操作を実行してください。

- [「C++ AMP の概要」](../../parallel/amp/cpp-amp-overview.md)を参照してください。

- [タイルを使用して](../../parallel/amp/using-tiles.md)読み取ります。

- Windows 7 または Windows Server 2008 R2 以降を実行していることを確認します。

### <a name="to-create-the-project"></a>プロジェクトを作成するには

新しいプロジェクトを作成する手順は、インストールされている Visual Studio のバージョンによって異なります。 優先するバージョンの Visual Studio のドキュメントを表示するには、 **[バージョン]** セレクター コントロールを使用します。 このページの目次の一番上にあります。

::: moniker range="msvc-160"

### <a name="to-create-the-project-in-visual-studio-2019"></a>Visual Studio 2019 でプロジェクトを作成するには

1. メニュー バーで、 **[ファイル]** > **[新規作成]** > **[プロジェクト]** の順に選択して、 **[新しいプロジェクトの作成]** ダイアログ ボックスを開きます。

1. ダイアログの上部で、 **[言語]** を **[C++]** に、 **[プラットフォーム]** を **[Windows]** に、 **[プロジェクト タイプ]** を **[コンソール]** に設定します。

1. フィルター処理されたプロジェクトの種類の一覧から [ **空のプロジェクト** ] を選択し、[ **次へ**] をクリックします。 次のページで、[**名前**] ボックスに「 *matrixmultiply.cpp* 」と入力し、プロジェクトの名前を指定します。必要に応じて、プロジェクトの場所を指定します。

   ![新しいコンソールアプリ](../../build/media/mathclient-project-name-2019.png "新しいコンソールアプリ")

1. **[作成]** ボタンを選択してクライアント プロジェクトを作成します。

1. **ソリューションエクスプローラー** で、[**ソースファイル**] のショートカットメニューを開き、[新しい項目の **追加**] を選択し > ます。

1. [**新しい項目の追加**] ダイアログボックスで、[ **C++ ファイル (.cpp)**] を選択し、[**名前**] ボックスに「 *matrixmultiply.cpp* 」と入力して、[**追加**] をクリックします。

::: moniker-end

::: moniker range="<=msvc-150"

### <a name="to-create-a-project-in-visual-studio-2017-or-2015"></a>Visual Studio 2017 または2015でプロジェクトを作成するには

1. Visual Studio のメニューバーで、[**ファイル**] [ > **新規作成**] [プロジェクト] の順に選択し > ます。

1. [テンプレート] ウィンドウの [ **インストール済み** ] で、[ **Visual C++**] を選択します。

1. [**空のプロジェクト**] を選択し、[**名前**] ボックスに「 *matrixmultiply.cpp* 」と入力して、[ **OK** ] をクリックします。

1. **[次へ]** ボタンをクリックします。

1. **ソリューションエクスプローラー** で、[**ソースファイル**] のショートカットメニューを開き、[新しい項目の **追加**] を選択し > ます。

1. [**新しい項目の追加**] ダイアログボックスで、[ **C++ ファイル (.cpp)**] を選択し、[**名前**] ボックスに「 *matrixmultiply.cpp* 」と入力して、[**追加**] をクリックします。

::: moniker-end

## <a name="multiplication-without-tiling"></a>タイルを使用しない乗算

ここでは、次のように定義されている 2 つの行列 A と B の乗算を考えます。

![3&#45;&#45;2 つのマトリックス A](../../parallel/amp/media/campmatrixanontiled.png "3&#45;&#45;2 つのマトリックス A")

![2&#45;&#45;3 マトリックス B](../../parallel/amp/media/campmatrixbnontiled.png "2&#45;&#45;3 マトリックス B")

A は、3 × 2 の行列であり、B は 2 × 3 の行列です。 A と B を乗算した積は、次のような 3 × 3 の行列になります。 この積は、要素ごとに A の行と B の列を乗算することによって計算されます。

![3&#45;&#45;3 製品マトリックス](../../parallel/amp/media/campmatrixproductnontiled.png "3&#45;&#45;3 製品マトリックス")

### <a name="to-multiply-without-using-c-amp"></a>C++ AMP を使用せずに乗算するには

1. MatrixMultiply.cpp を開き、次のコードを使用して既存のコードを置き換えます。

   ```cpp
   #include <iostream>

   void MultiplyWithOutAMP() {
       int aMatrix[3][2] = {{1, 4}, {2, 5}, {3, 6}};
       int bMatrix[2][3] = {{7, 8, 9}, {10, 11, 12}};
       int product[3][3] = {{0, 0, 0}, {0, 0, 0}, {0, 0, 0}};

       for (int row = 0; row < 3; row++) {
           for (int col = 0; col < 3; col++) {
               // Multiply the row of A by the column of B to get the row, column of product.
               for (int inner = 0; inner < 2; inner++) {
                   product[row][col] += aMatrix[row][inner] * bMatrix[inner][col];
               }
               std::cout << product[row][col] << "  ";
           }
           std::cout << "\n";
       }
   }

   int main() {
       MultiplyWithOutAMP();
       getchar();
   }
   ```

   このアルゴリズムは、行列乗算の定義の単純な実装です。 計算時間を短縮するスレッド アルゴリズムや並列アルゴリズムは使用していません。

1. メニュー バーで、 **[ファイル]**  >  **[すべてを保存]** の順に選択します。

1. F5 キーを **押し** てデバッグを開始し、出力が正しいことを確認します。

1. **Enter キーを押して** アプリケーションを終了します。

### <a name="to-multiply-by-using-c-amp"></a>C++ AMP を使用して乗算するには

1. MatrixMultiply.cpp で、`main` のメソッドの前に次のコードを追加します。

   ```cpp
   void MultiplyWithAMP() {
   int aMatrix[] = { 1, 4, 2, 5, 3, 6 };
   int bMatrix[] = { 7, 8, 9, 10, 11, 12 };
   int productMatrix[] = { 0, 0, 0, 0, 0, 0, 0, 0, 0 };

   array_view<int, 2> a(3, 2, aMatrix);

   array_view<int, 2> b(2, 3, bMatrix);

   array_view<int, 2> product(3, 3, productMatrix);

   parallel_for_each(product.extent,
      [=] (index<2> idx) restrict(amp) {
          int row = idx[0];
          int col = idx[1];
          for (int inner = 0; inner <2; inner++) {
              product[idx] += a(row, inner)* b(inner, col);
          }
      });

   product.synchronize();

   for (int row = 0; row <3; row++) {
      for (int col = 0; col <3; col++) {
          //std::cout << productMatrix[row*3 + col] << "  ";
          std::cout << product(row, col) << "  ";
      }
      std::cout << "\n";
     }
   }
   ```

   この AMP コードは、非 AMP コードに似ています。 を呼び出すと、 `parallel_for_each` の各要素に対して1つのスレッドが開始され、 `product.extent` **`for`** 行と列のループが置き換えられます。 行と列のセルの値は `idx` で使用できます。 `array_view` 演算子とインデックス変数、または `[]` 演算子と行と列の変数を使用することによって、`()` のオブジェクトの要素にアクセスできます。 この例では両方の方法を示します。 `array_view::synchronize` メソッドは `product` の変数に `productMatrix` 変数の値をコピーします。

1. 次の `include` ステートメントを **`using`** matrixmultiply.cpp の先頭に追加します。

   ```cpp
   #include <amp.h>
   using namespace concurrency;
   ```

1. `main` メソッドを呼び出すように `MultiplyWithAMP` メソッドを変更します。

   ```cpp
   int main() {
       MultiplyWithOutAMP();
       MultiplyWithAMP();
       getchar();
   }
   ```

1. **Ctrl** + **F5** キーを押してデバッグを開始し、出力が正しいことを確認します。

1. **Space** キーを押してアプリケーションを終了します。

## <a name="multiplication-with-tiling"></a>タイルを使用する乗算

タイルは、タイルと呼ばれる、同じサイズのサブセットにデータをパーティション分割するための手法です。 タイルを使用する場合、3 つ点が異なります。

- `tile_static` 変数を作成できます。 `tile_static` 空間のデータへのアクセスは、グローバル空間内のデータへのアクセスよりも何倍も高速になる場合があります。 各タイルについて `tile_static` 変数のインスタンスが作成され、タイル内のすべてのスレッドがこの変数にアクセスできます。 タイルの主な利点は、`tile_static` へのアクセスによるパフォーマンスの向上です。

- [Tile_barrier:: wait](reference/tile-barrier-class.md#wait)メソッドを呼び出すと、指定したコード行で1つのタイル内のすべてのスレッドを停止できます。 スレッドが実行される順序を保証することはできません。ただ、1 個のタイル内のすべてのスレッドが、実行を続ける前に `tile_barrier::wait` の呼び出しで停止するだけです。

- `array_view` オブジェクト全体を基準とするスレッドのインデックス、およびタイルを基準とするインデックスにアクセスできます。 ローカル インデックスを使うと、コードが読みやすくなり、デバッグも容易になります。

行列乗算でタイルを活用するには、アルゴリズムによって、行列をタイルに分割し、すばやくアクセスできるようにタイルのデータを `tile_static` 変数にコピーする必要があります。 この例では、行列は同じサイズのサブ行列に分割されます。 積はサブ行列を乗算することによって得られます。 この例の 2 つの行列とその積は次のとおりです。

![4マトリックス A&#45;4&#45;](../../parallel/amp/media/campmatrixatiled.png "4マトリックス A&#45;4&#45;")

![4マトリックス B&#45;4&#45;](../../parallel/amp/media/campmatrixbtiled.png "4マトリックス B&#45;4&#45;")

![4&#45;&#45;4 製品マトリックス](../../parallel/amp/media/campmatrixproducttiled.png "4&#45;&#45;4 製品マトリックス")

この行列は、次のように定義された 4 個の 2 × 2 の行列に分割されます。

![4&#45;&#45;4 マトリックス× 2&#45;2 つのサブ&#45;マトリックスによっ&#45;てパーティション分割されます。](../../parallel/amp/media/campmatrixapartitioned.png "4&#45;&#45;4 マトリックス× 2&#45;2 つのサブ&#45;マトリックスによっ&#45;てパーティション分割されます。")

![4&#45;&#45;4 つのマトリックス B によっ&#45;て 2&#45;にパーティション分割されている4つのサブ&#45;マトリックス](../../parallel/amp/media/campmatrixbpartitioned.png "4&#45;&#45;4 つのマトリックス B によっ&#45;て 2&#45;にパーティション分割されている4つのサブ&#45;マトリックス")

A と B の積は、次のように記述し、計算できます:

![4&#45;&#45;4 つのマトリックス A B が 2&#45;にパーティション分割され&#45;ている2つのサブ&#45;マトリックス](../../parallel/amp/media/campmatrixproductpartitioned.png "4&#45;&#45;4 つのマトリックス A B が 2&#45;にパーティション分割され&#45;ている2つのサブ&#45;マトリックス")

行列 `a` ～ `h` は 2 × 2 の行列であるため、すべての積とその合計も 2 × 2 の行列になります。 また、A と B の積は、4×4の行列になります。 アルゴリズムをすばやく確認するには、積の最初の行、最初の列の要素の値を計算します。 この例では、`ae + bg` の最初の行と最初の列の要素の値です。 各項について、`ae` と `bg` の最初の列と最初の行のみ計算する必要があります。 `ae` の値は `(1 * 1) + (2 * 5) = 11` です。 `bg` の値は `(3 * 1) + (4 * 5) = 23` です。 最終的な値は `11 + 23 = 34` となり、正しい値です。

このアルゴリズムを実装するには、コードで次のように処理します。

- `tiled_extent` の呼び出しで `extent` オブジェクトではなく `parallel_for_each` オブジェクトを使用します。

- `tiled_index` の呼び出しで `index` オブジェクトではなく `parallel_for_each` オブジェクトを使用します。

- サブ行列を保持する `tile_static` 変数を作成します。

- `tile_barrier::wait` メソッドを使用して、サブ行列の積を計算するためのスレッドを停止します。

### <a name="to-multiply-by-using-amp-and-tiling"></a>AMP とタイルを使用して乗算するには

1. MatrixMultiply.cpp で、`main` のメソッドの前に次のコードを追加します。

   ```cpp
   void MultiplyWithTiling() {
       // The tile size is 2.
       static const int TS = 2;

       // The raw data.
       int aMatrix[] = { 1, 2, 3, 4, 5, 6, 7, 8, 1, 2, 3, 4, 5, 6, 7, 8 };
       int bMatrix[] = { 1, 2, 3, 4, 5, 6, 7, 8, 1, 2, 3, 4, 5, 6, 7, 8 };
       int productMatrix[] = { 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0 };

       // Create the array_view objects.
       array_view<int, 2> a(4, 4, aMatrix);
       array_view<int, 2> b(4, 4, bMatrix);
       array_view<int, 2> product(4, 4, productMatrix);

       // Call parallel_for_each by using 2x2 tiles.
       parallel_for_each(product.extent.tile<TS, TS>(),
           [=] (tiled_index<TS, TS> t_idx) restrict(amp)
           {
               // Get the location of the thread relative to the tile (row, col)
               // and the entire array_view (rowGlobal, colGlobal).
               int row = t_idx.local[0];
               int col = t_idx.local[1];
               int rowGlobal = t_idx.global[0];
               int colGlobal = t_idx.global[1];
               int sum = 0;

               // Given a 4x4 matrix and a 2x2 tile size, this loop executes twice for each thread.
               // For the first tile and the first loop, it copies a into locA and e into locB.
               // For the first tile and the second loop, it copies b into locA and g into locB.
               for (int i = 0; i < 4; i += TS) {
                   tile_static int locA[TS][TS];
                   tile_static int locB[TS][TS];
                   locA[row][col] = a(rowGlobal, col + i);
                   locB[row][col] = b(row + i, colGlobal);
                   // The threads in the tile all wait here until locA and locB are filled.
                   t_idx.barrier.wait();

                   // Return the product for the thread. The sum is retained across
                   // both iterations of the loop, in effect adding the two products
                   // together, for example, a*e.
                   for (int k = 0; k < TS; k++) {
                       sum += locA[row][k] * locB[k][col];
                   }

                   // All threads must wait until the sums are calculated. If any threads
                   // moved ahead, the values in locA and locB would change.
                   t_idx.barrier.wait();
                   // Now go on to the next iteration of the loop.
               }

               // After both iterations of the loop, copy the sum to the product variable by using the global location.
               product[t_idx.global] = sum;
           });

       // Copy the contents of product back to the productMatrix variable.
       product.synchronize();

       for (int row = 0; row <4; row++) {
           for (int col = 0; col <4; col++) {
               // The results are available from both the product and productMatrix variables.
               //std::cout << productMatrix[row*3 + col] << "  ";
               std::cout << product(row, col) << "  ";
           }
           std::cout << "\n";
       }
   }
   ```

   この例は、タイルを使用しない例とは大きく異なります。 このコードでは、次のような概念的な手順を使用します。
   1. `a` の tile[0,0] の要素を `locA` にコピーします。 `b` の tile[0,0] の要素を `locB` にコピーします。 `product` はタイル化されていますが、`a` と `b` はタイル化されていないことに注意してください。 したがって、`a, b` および `product` にアクセスするにはグローバル インデックスを使用します。 `tile_barrier::wait` の呼び出しは不可欠です。 これは、`locA` と `locB` の両方が設定されるまで、タイル内のすべてのスレッドを停止します。

   1. `locA` と `locB` を乗算し、その結果を `product` に代入します。

   1. のタイル [0, 1] の要素を `a` にコピー `locA` します。 のタイル [1, 0] の要素を `b` にコピー `locB` します。

   1. `locA` と `locB` を乗算し、その結果を `product` に既に存在する結果に加算します。

   1. tile[0,0] の乗算が完了しました。

   1. 他の 4 個のタイルについても手順を繰り返します。 タイル用のインデックスはないため、スレッドは任意の順序で実行できます。 各スレッドの実行時に、各タイルについて `tile_static` 変数が適切に作成され、`tile_barrier::wait` の呼び出しによってプログラム フローが制御されます。

   1. アルゴリズムを詳しく調べると、各サブ行列は `tile_static` のメモリに 2 回読み込まれていることがわかります。 このデータ転送には時間がかかります。 ただし、データが `tile_static` のメモリにある場合、データへのアクセスははるかに高速です。 積を計算するにはサブ行列内の値に繰り返しアクセスする必要があるため、全体的なパフォーマンスは向上します。 最適なアルゴリズムとタイルのサイズを見つけるために、各アルゴリズムについて実験を行う必要があります。

   非 AMP と非タイルの例では、積を計算するために、A と B の各要素がグローバル メモリから 4 回アクセスされます。 タイルの例では、各要素がグローバル メモリから 2 回、`tile_static` のメモリから 4 回アクセスされます。 これは大幅なパフォーマンスの向上ではありません。 ただし、A と B が 1024 × 1024 の行列であり、タイルのサイズが 16 である場合は、パフォーマンスが大幅に向上します。 この場合には、各要素が、`tile_static` のメモリに 16 回だけコピーされ、`tile_static` のメモリから 1024 回アクセスされます。

1. 以下に示すように、main メソッドを変更し `MultiplyWithTiling` てメソッドを呼び出します。

   ```cpp
   int main() {
       MultiplyWithOutAMP();
       MultiplyWithAMP();
       MultiplyWithTiling();
       getchar();
   }
   ```

1. **Ctrl** + **F5** キーを押してデバッグを開始し、出力が正しいことを確認します。

1. アプリケーションを終了するには、 **スペース** バーを押します。

## <a name="see-also"></a>関連項目

[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[チュートリアル: C++ AMP アプリケーションのデバッグ](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)
