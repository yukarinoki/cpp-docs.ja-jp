---
title: 例外処理 (C +/cli および C++/cli CX) |Microsoft Docs
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- structured exception handling [C++], managed exceptions
- Exception class, managed applications
- exception handling
- C++ exception handling
- exception handling, types of
- System::Exception class in managed applications
ms.assetid: ccb11fe8-6938-41ac-b477-a183e85865b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7d070cc223f90f84bd52176ee7e50dbbfa441789
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2018
ms.locfileid: "49328130"
---
# <a name="exception-handling--ccli-and-ccx"></a>例外処理 (C +/cli および C++/cli CX)

コンパイルされたアプリケーション、`/ZW`コンパイラ オプションまたは`/clr`コンパイラ オプションの両方を使用して*例外*プログラムの実行中に予期しないエラーを処理します。 次のトピックについて説明して、C + での例外処理/cli/CX または C++/cli CLI アプリケーション。

## <a name="in-this-section"></a>このセクションの内容

[マネージド例外の使用についての基本概念](../dotnet/basic-concepts-in-using-managed-exceptions.md)<br/>
について説明します例外のスローとを使用して**お試しください**/**キャッチ**ブロックします。

[例外処理動作/clr での相違点](../dotnet/differences-in-exception-handling-behavior-under-clr.md)<br/>
C++ 例外処理の標準の動作の相違点をについて説明します。

[finally](../dotnet/finally.md)<br/>
使用する方法について説明します、finally キーワード。

[方法: グローバル例外ハンドラーを定義およびインストールする](../dotnet/how-to-define-and-install-a-global-exception-handler.md)<br/>
どの未処理の例外を示しますキャプチャできます。

[方法: MSIL からスローされるネイティブ コードの例外をキャッチする](../dotnet/how-to-catch-exceptions-in-native-code-thrown-from-msil.md)<br/>
ネイティブ コードで CLR と C++ の例外をキャッチする方法について説明します。

[方法: グローバル例外ハンドラーを定義およびインストールする](../dotnet/how-to-define-and-install-a-global-exception-handler.md)<br/>
すべての未処理の例外をキャッチする方法を示します。

## <a name="related-sections"></a>関連項目

[例外処理](../cpp/exception-handling-in-visual-cpp.md)<br/>
標準の C++ の例外処理について説明します。

## <a name="see-also"></a>関連項目

[Component Extensions for .NET と UWP](../windows/component-extensions-for-runtime-platforms.md)