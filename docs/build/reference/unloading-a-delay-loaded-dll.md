---
title: 遅延読み込みした DLL のアンロード
ms.date: 11/04/2016
helpviewer_keywords:
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.assetid: 6463bc71-020e-4aff-a4ca-90360411c54e
ms.openlocfilehash: 1895bf12cb195ef7b4555d400badf112d377547b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211919"
---
# <a name="unloading-a-delay-loaded-dll"></a>遅延読み込みした DLL のアンロード

既定で指定された遅延読み込みヘルパーは、遅延読み込み記述子に、pUnloadIAT フィールドに元のインポートアドレステーブル (IAT) のポインターとコピーが含まれているかどうかを確認します。 その場合は、リスト内のポインターをインポート遅延記述子に保存します。 これにより、ヘルパー関数は dll を名前で検索し、DLL の明示的なアンロードをサポートできます。

遅延読み込みされた DLL を明示的にアンロードするための、関連する構造体と関数を次に示します。

```cpp
//
// Unload support from delayimp.h
//

// routine definition; takes a pointer to a name to unload

ExternC
BOOL WINAPI
__FUnloadDelayLoadedDLL2(LPCSTR szDll);

// structure definitions for the list of unload records
typedef struct UnloadInfo * PUnloadInfo;
typedef struct UnloadInfo {
    PUnloadInfo     puiNext;
    PCImgDelayDescr pidd;
    } UnloadInfo;

// from delayhlp.cpp
// the default delay load helper places the unloadinfo records in the
// list headed by the following pointer.
ExternC
PUnloadInfo __puiHead;
```

UnloadInfo 構造体は、 **LocalAlloc**と**LocalFree**の実装をそれぞれ演算子と演算子として使用する C++ クラスを使用して実装され **`new`** **`delete`** ます。 これらのオプションは、リストの先頭として __puiHead を使用して、標準のリンクリストに保持されます。

__FUnloadDelayLoadedDLL を呼び出すと、読み込まれた Dll の一覧で指定した名前が検索されます (完全一致が必要です)。 見つかった場合は、pUnloadIAT 内の IAT のコピーが、実行されている IAT の一番上にコピーされてサンクポインターが復元されます。ライブラリは**FreeLibrary**で解放され、一致する**UnloadInfo**レコードはリストから削除されて削除され、TRUE が返されます。

関数 __FUnloadDelayLoadedDLL2 の引数は大文字と小文字が区別されます。 たとえば、次のように指定します。

```cpp
__FUnloadDelayLoadedDLL2("user32.DLL");
```

ではありません。

```cpp
__FUnloadDelayLoadedDLL2("User32.DLL");.
```

## <a name="see-also"></a>関連項目

[ヘルパー関数について](understanding-the-helper-function.md)
