---
description: '詳細情報: 純粋なコードと検証可能なコード (C++/CLI)'
title: 純粋なコードと検証可能なコード (C++/CLI)
ms.date: 11/04/2016
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
ms.openlocfilehash: 64224f7f462b5e11e522648a5b64ec9d568dc53f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276765"
---
# <a name="pure-and-verifiable-code-ccli"></a>純粋で検証可能なコード (C++/CLI)

.NET プログラミングの場合、Visual Studio 2017 の Visual C++ では、 [/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md) コンパイラオプションを使用した混合アセンブリの作成がサポートされています。 **/Clr: pure** オプションと **clr: Safe** オプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。 コードを安全または検証可能にする必要がある場合は、C# に移植することをお勧めします。

## <a name="mixed-clr"></a>混合 (/clr)

混合アセンブリ ( **/clr** でコンパイルされる) には、アンマネージ部分とマネージ部分の両方が含まれており、.net 機能を使用できますが、ネイティブコードが含まれています。 このため、プロジェクト全体を書き直すことなく、.NET 機能を使用するようにアプリケーションやコンポーネントを更新できます。 マネージコードとネイティブコードをこの方法で混在させるために Visual C++ を使用することを、C++ Interop と呼びます。 詳細については、「 [混在 (ネイティブおよびマネージ) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md) 」と「 [ネイティブと .Net の相互運用性](../dotnet/native-and-dotnet-interoperability.md)」を参照してください。

マネージアセンブリからのネイティブ Dll への呼び出しは、P/Invoke を使用してコンパイルされますが、セキュリティ設定によっては実行時に失敗する可能性があります。

コンパイラは渡されますが確認不可能なアセンブリとなる 1 つのコーディング例があります。スコープ解決演算子を使用し、オブジェクト インスタンスを通じて仮想関数を呼び出す場合です。  (例: `MyObj -> A::VirtualFunction();`)。

## <a name="see-also"></a>関連項目

- [C++/CLI を使用した .NET プログラミング (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
