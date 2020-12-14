---
description: 詳細については、Visual C++ 6.0 以降の DLL 遅延読み込みヘルパー関数の変更に関するページを参照してください。
title: Visual C++ 6.0 以降の DLL 遅延読み込みヘルパー関数の変更点
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, what's changed
- PFromRva method
- __delayLoadHelper2 function
- helper functions, what's changed
ms.assetid: 99f0be69-105d-49ba-8dd5-3be7939c0c72
ms.openlocfilehash: 0141467aab0b804cf82d21c15510d8f9941853a6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182490"
---
# <a name="changes-in-the-dll-delayed-loading-helper-function-since-visual-c-60"></a>Visual C++ 6.0 以降の DLL 遅延読み込みヘルパー関数の変更点

コンピューターに複数のバージョンの Visual C++ がある場合、または独自のヘルパー関数を定義した場合は、DLL 遅延読み込みヘルパー関数に加えられた変更によって影響を受ける可能性があります。 次に例を示します。

- **__delayLoadHelper** が **__delayLoadHelper2**

- **__pfnDliNotifyHook** が **__pfnDliNotifyHook2**

- **__pfnDliFailureHook** が **__pfnDliFailureHook2**

- **__FUnloadDelayLoadedDLL** が **__FUnloadDelayLoadedDLL2**

> [!NOTE]
> 既定のヘルパー関数を使用している場合、これらの変更はユーザーに影響しません。 リンカーの呼び出し方法に関する変更はありません。

## <a name="multiple-versions-of-visual-c"></a>複数バージョンの Visual C++

コンピューターに複数のバージョンの Visual C++ がある場合は、リンカーが delayimp .lib と一致していることを確認してください。 不一致がある場合は、 `___delayLoadHelper2@8` または `___delayLoadHelper@8` 未解決の外部シンボルとして、またはのいずれかのリンカーエラー報告が表示されます。 前者は古い delayimp .lib を使用する新しいリンカーを意味し、後者は新しい delayimp .lib を持つ古いリンカーを意味します。

未解決のリンカーエラーが発生した場合は、その代わりに定義されているヘルパー関数を確認するためにヘルパー関数を含めることが予想される場合は、 [dumpbin/linkermember](linkermember.md): 1 を実行します。 ヘルパー関数は、オブジェクトファイルでも定義できます。 [dumpbin/symbols](symbols.md) を実行し、を検索し `delayLoadHelper(2)` ます。

Visual C++ 6.0 リンカーがあることがわかっている場合は、次のようになります。

- 遅延読み込みヘルパーの .lib または .obj ファイルに対して dumpbin を実行し、 **__delayLoadHelper2** が定義されているかどうかを判断します。 それ以外の場合、リンクは失敗します。

- 遅延読み込みヘルパーの .lib ファイルまたは .obj ファイルで **__delayLoadHelper** を定義します。

## <a name="user-defined-helper-function"></a>User-Defined ヘルパー関数

独自のヘルパー関数を定義し、現在のバージョンの Visual C++ を使用している場合は、次の手順を実行します。

- ヘルパー関数の名前を **__delayLoadHelper2** に変更します。

- 遅延記述子 (delayimp の ImgDelayDescr) のポインターは、絶対アドレス (VAs) から相対アドレス (RVAs) に変更され、32と64ビットの両方のプログラムで期待どおりに動作するため、これらをポインターに変換する必要があります。 新しい関数が導入されました。 PFromRva は、delayhlp にあります。 この関数を記述子の各フィールドに対して使用して、それらを32または64ビットのポインターに変換し直すことができます。 既定の遅延読み込みヘルパー関数は、例として使用するのに適したテンプレートになります。

## <a name="load-all-imports-for-a-delay-loaded-dll"></a>Delay-Loaded DLL のすべてのインポートを読み込みます

リンカーは、遅延読み込みの対象として指定した DLL から、すべてのインポートを読み込むことができます。 詳細については [、「Delay-Loaded DLL のすべてのインポートの読み込み](loading-all-imports-for-a-delay-loaded-dll.md) 」を参照してください。

## <a name="see-also"></a>関連項目

[ヘルパー関数について](understanding-the-helper-function.md)
