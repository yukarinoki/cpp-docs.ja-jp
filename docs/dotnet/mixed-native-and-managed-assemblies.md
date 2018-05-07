---
title: 混在 (ネイティブおよびマネージ) アセンブリ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], mixed assemblies
- /clr compiler option [C++], mixed assemblies
- managed code [C++], interoperability
- interoperability [C++], mixed assemblies
- mixed DLL loading [C++]
- mixed assemblies [C++], about mixed assemblies
- assemblies [C++], mixed
- mixed assemblies [C++]
- native code [C++], .NET interoperatibility
ms.assetid: 4299dfce-392f-4933-8bf0-5da2f0d1c282
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0ac18841d5050bc8fb849ac542dc298ce89c964f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="mixed-native-and-managed-assemblies"></a>混在 (ネイティブおよびマネージ) アセンブリ
混在アセンブリは、アンマネージ マシン語命令と MSIL 命令の両方を含むことができます。 これにより、混在アセンブリは、全体としてはアンマネージのコンポーネントとの互換性を維持しながら、.NET コンポーネントを呼び出したり、.NET コンポーネントから呼び出したりできます。 混在アセンブリを使用すると、開発者は、マネージ機能とアンマネージ機能が混在したアプリケーションを作成できます。 このため、混在アセンブリは、既存の Visual C++ アプリケーションを .NET プラットフォームに移行するのに理想的です。  
  
 たとえば、アンマネージ関数でのみ構成された既存のアプリケーションにできます .NET プラットフォームに 1 つのモジュールを再コンパイルして、 **/clr**コンパイラ スイッチ。 以降、このモジュールで .NET 機能を使用できるようになりますが、アプリケーションの残りの部分との互換性は維持されたままです。 この方法を使用すると、アプリケーションを要素ごとに少しずつ .NET プラットフォームに変換できます。 同じファイル内の関数ごとに、マネージ コードとアンマネージのコンパイルの間を決定することも (を参照してください[マネージ、アンマネージ](../preprocessor/managed-unmanaged.md))。  
  
 Visual C++ では、混合、純粋、および検証可能の 3 種類のマネージ アセンブリの生成をサポートしています。 後者 2 つは、後ほど[純粋なコードと検証可能なコード (C + + CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [方法:/clr:pure に移行](../dotnet/how-to-migrate-to-clr.md)  
 アプリケーションへの .NET 機能の導入またはアプリケーション内の .NET 機能の更新を行うための推奨処理手順について説明します。  
  
 [方法: MFC および ATL コードを使用して/clr のコンパイル](../dotnet/how-to-compile-mfc-and-atl-code-by-using-clr.md)  
 共通言語ランタイムをターゲットに既存の MFC および ATL プログラムをコンパイルする方法について説明します。  
  
 [混在アセンブリの初期化](../dotnet/initialization-of-mixed-assemblies.md)  
 "ローダー ロック" の問題とそのソリューションについて説明します。  
  
 [混在アセンブリのためのライブラリ サポート](../dotnet/library-support-for-mixed-assemblies.md)  
 ネイティブ ライブラリを使用する方法について説明 **/clr**コンパイルします。  
  
 [パフォーマンスに関する考慮事項](../dotnet/performance-considerations-for-interop-cpp.md)  
 混在アセンブリとデータ マーシャリングのパフォーマンスへの影響について説明します。  
  
 [アプリケーション ドメインと Visual C++](../dotnet/application-domains-and-visual-cpp.md)  
 アプリケーション ドメインに対する Visual C++ サポートについて説明します。  
  
 [ダブル サンキング](../dotnet/double-thunking-cpp.md)  
 マネージ関数のネイティブ エントリ ポイントのパフォーマンスへの影響について説明します。  
  
 [/Clr で CLR シャット ダウン時に消費して構築された COM オブジェクトの例外の回避](../dotnet/avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr.md)  
 コンパイルされた COM オブジェクトを使用するマネージ アプリケーションの適切なシャット ダウンする方法について説明 **/clr**です。  
  
 [方法: CRT ライブラリ DLL との依存関係を削除して部分信頼アプリケーションを作成する](../dotnet/create-a-partially-trusted-application.md)  
 Msvcm90.dll との依存関係を削除することによって、Visual C を使用して部分的に信頼された共通言語ランタイム アプリケーションを作成する方法について説明します。  
  
 混在アセンブリのコーディングのガイドラインの詳細についてを参照してください、MSDN の記事「: 概要の管理/管理されていないコードの相互運用性」で[ http://msdn.microsoft.com/netframework/default.aspx?pull=/library/dndotnet/html/manunmancode.asp](http://msdn.microsoft.com/netframework/default.aspx?pull=/library/dndotnet/html/manunmancode.asp)です。  
  
## <a name="see-also"></a>関連項目  
 [ネイティブと .NET の相互運用性](../dotnet/native-and-dotnet-interoperability.md)