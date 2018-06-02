---
title: 純粋と検証可能なコード (C + + CLI) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- /clr compiler option [C++], verifiable assemblies
- /clr compiler option [C++], mixed assemblies
- pure MSIL [C++]
- verifiable assemblies [C++]
- verifiably type-safe code [C++]
- /clr compiler option [C++], pure assemblies
- .NET Framework [C++], pure and verifiable code
- assemblies [C++], mixed code
- verifiable assemblies [C++], about verifiable assemblies
- mixed assemblies [C++], about mixed assemblies
- pure MSIL [C++], about pure code
- assemblies [C++], verifiable code
- mixed assemblies [C++]
- assemblies [C++], pure code
ms.assetid: 9050e110-fa11-4356-b56c-665187ff871c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 453bb40e94c1d345adbe22f8792b59d1e584499a
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704829"
---
# <a name="pure-and-verifiable-code-ccli"></a>純粋と検証可能なコード (C + + CLI)

.NET プログラミングに対して、Visual Studio 2017 での Visual C を使用して混在アセンブリの作成をサポートして、 [/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプション。 **/Clr: 純粋な**と **/clr:safe**オプションが Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。 コードが必要な場合も安全だ検証可能なお勧め c# に移植することとします。

## <a name="mixed-clr"></a>混合 (/clr)

混在アセンブリ (コンパイルした **/clr**) アンマネージ両方を含めること、および .NET 機能を利用できるようにする、管理対象の部分には、ネイティブ コードですが含まれています。 このため、プロジェクト全体を書き直すことなく、.NET 機能を使用するようにアプリケーションやコンポーネントを更新できます。 Visual C を使用して、この方法でマネージ コードとネイティブ コードを混在させると、C++ Interop は呼び出されます。 詳細については、次を参照してください。[混在 (ネイティブおよびマネージ) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)と[ネイティブ モードと .NET の相互運用性](../dotnet/native-and-dotnet-interoperability.md)です。

マネージ アセンブリから呼び出し P/invoke を使用してネイティブ Dll にコンパイルされますが、セキュリティ設定によっては実行時に失敗する可能性があります。

コンパイラは渡されますが確認不可能なアセンブリとなる 1 つのコーディング例があります。スコープ解決演算子を使用し、オブジェクト インスタンスを通じて仮想関数を呼び出す場合です。  たとえば、`MyObj -> A::VirtualFunction();` のように指定します。

## <a name="see-also"></a>関連項目

- [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

