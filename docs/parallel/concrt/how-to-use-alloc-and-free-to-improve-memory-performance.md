---
title: '方法: 割り当てを使用し、メモリのパフォーマンスを向上させるために無料'
ms.date: 11/04/2016
helpviewer_keywords:
- Alloc and Free, using [Concurrency Runtime]
- Using Alloc and Free [Concurrency Runtime]
ms.assetid: e1fab9e8-a97d-4104-bead-e95958db79f9
ms.openlocfilehash: f55bf360ac2b4c7162c1ed2b917ac6ce8c7cd11f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410020"
---
# <a name="how-to-use-alloc-and-free-to-improve-memory-performance"></a>方法: 割り当てを使用し、メモリのパフォーマンスを向上させるために無料

このドキュメントは、使用する方法を示します、 [concurrency::alloc](reference/concurrency-namespace-functions.md#alloc)と[concurrency::free](reference/concurrency-namespace-functions.md#free)メモリのパフォーマンスを向上させるために機能します。 ここでは、それぞれが `new` 演算子と `delete` 演算子を指定する、配列の 3 種類の要素を並行して反転するときの所要時間を比較します。

`Alloc` 関数と `Free` 関数は、複数のスレッドで `Alloc` と `Free` の両方を頻繁に呼び出す場合に最も役に立ちます。 ランタイムは、スレッドごとに個別のメモリ キャッシュを保持します。したがって、ランタイムは、ロックまたはメモリ バリアを使用せずにメモリを管理します。

## <a name="example"></a>例

それぞれが `new` 演算子と `delete` 演算子を指定する、3 種類の例を次に示します。 `new_delete`クラスはグローバル`new`と`delete`演算子、`malloc_free`クラスは、C ランタイムを使用して[malloc](../../c-runtime-library/reference/malloc.md)と[無料](../../c-runtime-library/reference/free.md)関数、および`Alloc_Free`クラスは、同時実行ランタイムを使用して`Alloc`と`Free`関数。

[!code-cpp[concrt-allocators#1](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_1.cpp)]

## <a name="example"></a>例

`swap` 関数および `reverse_array` 関数の例を次に示します。 `swap` 関数は、配列の指定されたインデックス位置の内容を交換します。 また、テンポラリ変数のヒープからメモリを割り当てます。 `reverse_array` 関数は、大きな配列を作成し、その配列を並行して複数回反転したときの所要時間を計算します。

[!code-cpp[concrt-allocators#2](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_2.cpp)]

## <a name="example"></a>例

それぞれが異なるメモリ割り当て方法を使用する `wmain`、`reverse_array`、および `new_delete` の各クラスを `malloc_free` 関数で操作したときの所要時間を計算する、`Alloc_Free` 関数の例を次に示します。

[!code-cpp[concrt-allocators#3](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_3.cpp)]

## <a name="example"></a>例

完全な例を次に示します。

[!code-cpp[concrt-allocators#4](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_4.cpp)]

この例では、4 つのプロセッサを備えたコンピューターで次のサンプル出力を生成します。

```Output
Took 2031 ms with new/delete.
Took 1672 ms with malloc/free.
Took 656 ms with Alloc/Free.
```

この例で、`Alloc` 関数と `Free` 関数を使用する例では、`Alloc` 関数と `Free` 関数が複数スレッドのメモリ ブロックを頻繁に割り当ておよび解放する操作に対して最適化されるため、最も優れたメモリ パフォーマンスが提供されます。

## <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付ける`allocators.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。

**cl.exe/EHsc allocators.cpp**

## <a name="see-also"></a>関連項目

[メモリ管理関数](../../parallel/concrt/memory-management-functions.md)<br/>
[Alloc 関数](reference/concurrency-namespace-functions.md#alloc)<br/>
[Free 関数](reference/concurrency-namespace-functions.md#free)
