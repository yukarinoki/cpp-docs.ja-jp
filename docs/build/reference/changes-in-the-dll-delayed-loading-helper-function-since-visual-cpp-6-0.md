---
title: Visual C++ 6.0 以降の DLL 遅延読み込みヘルパー関数の変更点
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, what's changed
- PFromRva method
- __delayLoadHelper2 function
- helper functions, what's changed
ms.assetid: 99f0be69-105d-49ba-8dd5-3be7939c0c72
ms.openlocfilehash: 536729e27c89d068957ea451355957e4a35348ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320610"
---
# <a name="changes-in-the-dll-delayed-loading-helper-function-since-visual-c-60"></a>Visual C++ 6.0 以降の DLL 遅延読み込みヘルパー関数の変更点

コンピュータに複数のバージョンの Visual C++ がある場合、または独自のヘルパー関数を定義している場合は、DLL の遅延読み込みヘルパー関数に対する変更の影響を受ける可能性があります。 次に例を示します。

- **__delayLoadHelper**は今 **__delayLoadHelper2**

- **__pfnDliNotifyHook**は今 **__pfnDliNotifyHook2**

- **__pfnDliFailureHook**は**現在__pfnDliFailureHook2**

- **__FUnloadDelayLoadedDLL**は今 **__FUnloadDelayLoadedDLL2**

> [!NOTE]
> 既定のヘルパー関数を使用している場合、これらの変更は影響を与えありません。 リンカーの呼び出し方法に関する変更はありません。

## <a name="multiple-versions-of-visual-c"></a>複数バージョンの Visual C++

コンピューターに複数のバージョンの Visual C++ がある場合は、リンカーが delayimp.lib と一致することを確認してください。 不一致がある場合は、リンカー エラー報告のいずれかまたは`___delayLoadHelper2@8``___delayLoadHelper@8`未解決の外部シンボルとして表示されます。 前者は古い delayimp.lib を持つ新しいリンカーを意味し、後者は新しい delayimp.lib を持つ古いリンカーを意味します。

未解決のリンカー エラーが発生した場合は、ヘルパー関数が含まれると予想される delayimp.lib で[dumpbin /linkermember](linkermember.md):1 を実行し、代わりにどのヘルパー関数が定義されているかを確認します。 ヘルパー関数はオブジェクトファイルで定義することもできます。[ダンプビン /シンボル](symbols.md)を実行し`delayLoadHelper(2)`、 を検索します。

Visual C++ 6.0 リンカーがわかっている場合は、次の手順を実行します。

- 遅延読み込みヘルパーの .lib ファイルまたは .obj ファイルで dumpbin を実行して **、__delayLoadHelper2**定義されているかどうかを判断します。 そうしないと、リンクは失敗します。

- 遅延読み込みヘルパーの .lib ファイルまたは .obj ファイルに **__delayLoadHelper**を定義します。

## <a name="user-defined-helper-function"></a>ユーザー定義ヘルパー関数

独自のヘルパー関数を定義し、現在のバージョンの Visual C++ を使用している場合は、次の操作を行います。

- ヘルパー関数の名前を **__delayLoadHelper2**に変更します。

- 遅延記述子 (delayimp.h の ImgDelayDescr) のポインターは、絶対アドレス (VA) から相対アドレス (RVA) に変更され、32 ビットと 64 ビットの両方のプログラムで期待どおりに動作するため、これらをポインターに戻す必要があります。 新しい関数が導入されました: PFromRva, delayhlp.cpp で見つかりました. 記述子の各フィールドでこの関数を使用して、それらを 32 ビットまたは 64 ビットのポインターに変換できます。 既定の遅延読み込みヘルパー関数は、引き続き例として使用する適切なテンプレートです。

## <a name="load-all-imports-for-a-delay-loaded-dll"></a>遅延読み込み DLL のすべてのインポートを読み込む

リンカーは、遅延読み込みとして指定した DLL からすべてのインポートを読み込むことができます。 詳細については、「[遅延読み込み DLL のすべてのインポートを読み込む](loading-all-imports-for-a-delay-loaded-dll.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ヘルパー関数について](understanding-the-helper-function.md)
