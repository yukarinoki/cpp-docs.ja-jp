---
title: 混在 (ネイティブおよびマネージド) アセンブリ
ms.date: 09/18/2018
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
ms.openlocfilehash: 11bdfc98c64b2612129e10c002c68ee243bec7da
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "79544508"
---
# <a name="mixed-native-and-managed-assemblies"></a>混在 (ネイティブおよびマネージド) アセンブリ

混在アセンブリは、アンマネージ マシン語命令と MSIL 命令の両方を含むことができます。 これにより、ネイティブC++ライブラリとの互換性を維持しながら、.net コンポーネントによってを呼び出し、呼び出すことができます。 混合アセンブリを使用すると、開発者は .NET とネイティブC++コードを組み合わせて使用してアプリケーションを作成できます。

たとえば、ネイティブC++コード全体で構成される既存のライブラリを .net プラットフォームに取り込むには、 **/clr**コンパイラスイッチを使用して1つのモジュールだけを再コンパイルします。 以降、このモジュールで .NET 機能を使用できるようになりますが、アプリケーションの残りの部分との互換性は維持されたままです。 同じファイル内の関数ごとに、マネージコンパイルとネイティブコンパイルのどちらかを決定することもできます (「[マネージ、アンマネージ」を](../preprocessor/managed-unmanaged.md)参照してください)。

Visual C++は、 **/clr**コンパイラオプションを使用して、混合マネージアセンブリの生成だけをサポートします。 **/Clr: pure**および **/clr: safe**コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。 純粋または検証可能なマネージアセンブリが必要な場合は、を使用C#して作成することをお勧めします。

以前のバージョンの Microsoft C++コンパイラツールセットでは、混合、純粋、検証可能の3種類のマネージアセンブリの生成がサポートされていました。 後者の2つについては、 [「純粋C++で検証可能なコード (/cli)](../dotnet/pure-and-verifiable-code-cpp-cli.md)」で説明されています。

## <a name="in-this-section"></a>このセクションの内容

[方法:/clr に移行する](../dotnet/how-to-migrate-to-clr.md)<br/>
アプリケーションへの .NET 機能の導入またはアプリケーション内の .NET 機能の更新を行うための推奨処理手順について説明します。

[方法:/clr を使用して MFC および ATL コードをコンパイルする](../dotnet/how-to-compile-mfc-and-atl-code-by-using-clr.md)<br/>
共通言語ランタイムをターゲットに既存の MFC および ATL プログラムをコンパイルする方法について説明します。

[混在アセンブリの初期化](../dotnet/initialization-of-mixed-assemblies.md)<br/>
"ローダー ロック" の問題とそのソリューションについて説明します。

[混在アセンブリのためのライブラリ サポート](../dotnet/library-support-for-mixed-assemblies.md)<br/>
**/Clr**コンパイルでネイティブライブラリを使用する方法について説明します。

[パフォーマンスに関する考慮事項](../dotnet/performance-considerations-for-interop-cpp.md)<br/>
混在アセンブリとデータ マーシャリングのパフォーマンスへの影響について説明します。

[アプリケーション ドメインと Visual C++](../dotnet/application-domains-and-visual-cpp.md)<br/>
アプリケーション ドメインに対する Visual C++ サポートについて説明します。

[ダブルサンキング](../dotnet/double-thunking-cpp.md)<br/>
マネージド関数のネイティブ エントリ ポイントのパフォーマンスへの影響について説明します。

[/Clr でビルドされた COM オブジェクトを使用する場合の CLR シャットダウンでの例外の回避](../dotnet/avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr.md)<br/>
**/Clr**でコンパイルされた COM オブジェクトを使用するマネージアプリケーションを適切にシャットダウンする方法について説明します。

[方法: CRT ライブラリ DLL との依存関係を削除して部分信頼アプリケーションを作成する](../dotnet/create-a-partially-trusted-application.md)<br/>
Msvcm90 の依存関係を削除して、部分的に信頼さC++れた共通言語ランタイムアプリケーションをビジュアルを使用して作成する方法について説明します。

混合アセンブリのコーディングのガイドラインの詳細については、MSDN の記事「[マネージ/アンマネージコードの相互運用性の概要](/previous-versions/dotnet/articles/ms973872(v=msdn.10))」を参照してください。

## <a name="see-also"></a>参照

- [ネイティブと .NET の相互運用性](../dotnet/native-and-dotnet-interoperability.md)
