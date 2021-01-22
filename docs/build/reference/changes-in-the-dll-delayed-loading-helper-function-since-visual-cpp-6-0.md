---
description: 詳細については、Visual C++ 6.0 以降の DLL 遅延読み込みヘルパー関数の変更に関するページを参照してください。
title: Visual C++ 6.0 以降の DLL 遅延読み込みヘルパー関数の変更点
ms.date: 01/19/2021
helpviewer_keywords:
- delayed loading of DLLs, what's changed
- PFromRva method
- __delayLoadHelper2 function
- helper functions, what's changed
ms.openlocfilehash: a83d5e2895863efde396c48d68316e32aa42a2a1
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "98666967"
---
# <a name="changes-in-the-dll-delayed-loading-helper-function-since-visual-c-60"></a>Visual C++ 6.0 以降の DLL 遅延読み込みヘルパー関数の変更点

コンピューターに複数のバージョンの Visual C++ がある場合、または独自のヘルパー関数を定義した場合、DLL 遅延読み込みヘルパー関数に加えられた変更がユーザーに影響を与える可能性があります。 次に例を示します。

- **`__delayLoadHelper`** 現在の状態 `__delayLoadHelper2`

- `__pfnDliNotifyHook` は `__pfnDliNotifyHook2` になりました

- `__pfnDliFailureHook` は `__pfnDliFailureHook2` になりました

- `__FUnloadDelayLoadedDLL` は `__FUnloadDelayLoadedDLL2` になりました

> [!NOTE]
> 既定のヘルパー関数を使用している場合、これらの変更は影響を与えません。 リンカーの呼び出し方法に関する変更はありません。

## <a name="multiple-versions-of-visual-c"></a>複数バージョンの Visual C++

コンピューターに複数のバージョンの Visual C++ がある場合は、リンカーがと一致していることを確認し *`delayimp.lib`* ます。 不一致がある場合 `___delayLoadHelper2@8` は、または `___delayLoadHelper@8` 未解決の外部シンボルとして、またはのいずれかのリンカーエラー報告が表示されます。 前者は古いを持つ新しいリンカーを意味 *`delayimp.lib`* し、後者は新しいを持つ古いリンカーを意味し *`delayimp.lib`* ます。

未解決のリンカーエラーが発生した場合は、に対して実行し、 [`dumpbin /linkermember:1`](linkermember.md) *`delayimp.lib`* ヘルパー関数が定義されているかどうかを確認します。 ヘルパー関数は、オブジェクトファイルでも定義できます。 [`dumpbin /symbols`](symbols.md) を実行し、 `delayLoadHelper` またはを探し `delayLoadHelper2` ます。

Visual C++ 6.0 リンカーがあることがわかっている場合は、次のようになります。

- **`dumpbin`** 遅延読み込みヘルパーまたはファイルでを実行し *`.lib`* て、 *`.obj`* が定義されているかどうかを判断 `__delayLoadHelper2` します。 それ以外の場合、リンクは失敗します。

- `__delayLoadHelper`遅延読み込みヘルパー *`.lib`* またはファイルでを定義 *`.obj`* します。

## <a name="user-defined-helper-function"></a>ユーザー定義のヘルパー関数

独自のヘルパー関数を定義し、現在のバージョンの Visual C++ を使用している場合は、次の手順を実行します。

- ヘルパー関数の名前をに変更し `__delayLoadHelper2` ます。

- 遅延記述子内のポインター () は `ImgDelayDescr` 、 *`delayimp.h`* 絶対アドレス (VAs) から相対アドレス (RVAs) に変更され、32ビットプログラムと64ビットプログラムの両方で期待どおりに動作するようになったため、これらの RVAs をポインターに変換する必要があります。 新しい関数が導入されました。 `PFromRva` 「」を参照 *`delayhlp.cpp`* してください。 この関数は、記述子の各フィールドに対して使用して、32ビットまたは64ビットのポインターに変換することができます。 既定の遅延読み込みヘルパー関数は、例として使用するのに適したテンプレートになります。

## <a name="load-all-imports-for-a-delay-loaded-dll"></a>遅延読み込みされた DLL のすべてのインポートを読み込みます

リンカーは、遅延読み込みの対象として指定した DLL から、すべてのインポートを読み込むことができます。 詳細については、「 [遅延読み込みされた DLL のすべてのインポートの読み込み](loading-all-imports-for-a-delay-loaded-dll.md)」を参照してください。

## <a name="see-also"></a>こちらもご覧ください

[ヘルパー関数について](understanding-the-helper-function.md)
