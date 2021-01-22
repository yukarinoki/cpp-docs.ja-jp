---
description: 遅延読み込みされた DLL のアンロードに関する詳細情報
title: 遅延読み込みされた DLL のアンロード
ms.date: 01/19/2021
helpviewer_keywords:
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.openlocfilehash: 2ac898d56609ebb3aadc57ea8df00fa63fcbc3f0
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667243"
---
# <a name="unload-a-delay-loaded-dll"></a>遅延読み込みされた DLL のアンロード

既定の遅延読み込みヘルパーは、遅延読み込み記述子に、フィールドに元のインポートアドレステーブル (IAT) のポインターとコピーが含まれているかどうかを確認し `pUnloadIAT` ます。 その場合、ヘルパーは、リスト内のポインターをインポート遅延記述子に保存します。 このエントリにより、ヘルパー関数は dll を名前で検索できるようになり、DLL の明示的なアンロードがサポートされます。

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

`UnloadInfo`構造体は、およびの実装をおよびとして使用する C++ クラスを使用して実装され `LocalAlloc` `LocalFree` `operator new` `operator delete` ます。 これらのオプションは、 `__puiHead` リストの先頭としてを使用する標準のリンクリストに保持されます。

を呼び出すと `__FUnloadDelayLoadedDLL` 、読み込まれた dll の一覧で指定した名前の検索が試行されます。 (完全一致が必要です)。見つかった場合は、の IAT のコピー `pUnloadIAT` が、実行されている iat の先頭にコピーされ、サンクポインターが復元されます。 次に、を使用してライブラリが解放され、 `FreeLibrary` 一致するレコードがリストからリンク解除されて削除され、 `UnloadInfo` `TRUE` が返されます。

関数の引数で `__FUnloadDelayLoadedDLL2` は、大文字と小文字が区別されます。 たとえば、次のように指定します。

```cpp
__FUnloadDelayLoadedDLL2("user32.dll");
```

ではありません。

```cpp
__FUnloadDelayLoadedDLL2("User32.DLL");.
```

## <a name="see-also"></a>こちらもご覧ください

[ヘルパー関数について](understanding-the-helper-function.md)
