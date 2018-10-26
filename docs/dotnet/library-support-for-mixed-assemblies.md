---
title: 混在アセンブリのライブラリのサポート |Microsoft Docs
ms.custom: ''
ms.date: 09/18/2018
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- msvcm90[d].dll
- mixed assemblies [C++], library support
- msvcmrt[d].lib
- libraries [C++], mixed assemblies
ms.assetid: 1229595c-9e9d-414d-b018-b4e4c727576d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8c3fec26f3e41c3edd2346ac2e1b9b1f6b98ba33
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50069621"
---
# <a name="library-support-for-mixed-assemblies"></a>混在アセンブリのためのライブラリ サポート

Visual C、C++ 標準ライブラリ、C ランタイム ライブラリ (CRT) の使用をサポートする、ATL と MFC でコンパイルされたアプリケーションの[/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)します。 これにより、既存のアプリケーションも .NET Framework の機能を使用するためにこれらのライブラリを使用できます。

> [!IMPORTANT]
> **/Clr: 純粋な**と **/clr:safe**コンパイラ オプションは Visual Studio 2015 で非推奨とされ、Visual Studio 2017 でサポートされていません。

このサポートには、次の DLL とインポート ライブラリが含まれています。

- 使用してコンパイルする場合、Msvcmrt [d] .lib **/clr**します。 このインポート ライブラリへのリンクを混在アセンブリ。

このサポートは、関連するいくつかの利点を提供します。

- CRT と C++ 標準ライブラリは、混合コードを利用します。 CRT と C++ 標準ライブラリが提供されているは検証可能な; できません。最終的には、呼び出しはネイティブ コードから使用するため引き続き同じ CRT と C++ 標準ライブラリにルーティングされます。

- 混合イメージで統一された例外の処理を修正します。

- 混合イメージ内の C++ 変数の静的な初期化します。

- マネージ コードで、AppDomain ごとと、プロセスごとの変数をサポートします。

- 混在モード Dll を Visual Studio 2003 以前のバージョンでのコンパイルに適用されるローダー ロックに関する問題を解決します。

さらに、このサポートには、次の制限事項が表示されます。

- コンパイルされるコードに、CRT DLL モデルのみがサポートされている **/clr**します。 サポートする静的な CRT ライブラリがない **/clr**をビルドします。

## <a name="see-also"></a>関連項目

- [混在 (ネイティブおよびマネージド) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)
