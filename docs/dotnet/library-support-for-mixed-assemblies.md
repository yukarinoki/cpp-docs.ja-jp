---
description: '詳細情報: ライブラリによる混合アセンブリのサポート'
title: 混在アセンブリのためのライブラリ サポート
ms.date: 09/18/2018
helpviewer_keywords:
- msvcm90[d].dll
- mixed assemblies [C++], library support
- msvcmrt[d].lib
- libraries [C++], mixed assemblies
ms.assetid: 1229595c-9e9d-414d-b018-b4e4c727576d
ms.openlocfilehash: d20069c2caa1cf46ebdb54907de586630d4ee71c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113715"
---
# <a name="library-support-for-mixed-assemblies"></a>混在アセンブリのためのライブラリ サポート

Visual C++ は、 [/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)を使用してコンパイルされたアプリケーションの C++ 標準ライブラリ、c ランタイムライブラリ (CRT)、ATL、MFC の使用をサポートしています。 これにより、これらのライブラリを使用する既存のアプリケーションでも .NET Framework 機能を使用できます。

> [!IMPORTANT]
> **/Clr: pure** および **/clr: safe** コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

このサポートには、次の DLL とインポートライブラリが含まれています。

- Msvcmrt.lib [d] .lib ( **/clr** を使用してコンパイルする場合)。 混合アセンブリは、このインポートライブラリにリンクします。

このサポートには、いくつかの関連する利点があります。

- CRT および C++ 標準ライブラリは、混合コードで使用できます。 指定された CRT および C++ 標準ライブラリは検証できません。最終的には、ネイティブコードから使用しているのと同じ CRT および C++ 標準ライブラリに呼び出しがルーティングされます。

- 混合イメージで統合された例外処理を修正します。

- 混合イメージでの C++ 変数の静的な初期化。

- マネージコードでの AppDomain ごとの変数とプロセスごとの変数のサポート。

- Visual Studio 2003 以前でコンパイルされた混合 Dll に適用されるローダーロックの問題を解決します。

また、このサポートには次の制限があります。

- **/Clr** でコンパイルされたコードでは、CRT DLL モデルのみがサポートされます。 **/Clr** ビルドをサポートする静的 CRT ライブラリはありません。

## <a name="see-also"></a>関連項目

- [混合 (ネイティブおよびマネージ) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)
