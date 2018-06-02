---
title: 混在アセンブリのライブラリのサポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: d4b584e0bacb1cb93cad33efdff807bb5fa9c8e2
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704112"
---
# <a name="library-support-for-mixed-assemblies"></a>混在アセンブリのためのライブラリ サポート

Visual C、C++ 標準ライブラリ、C ランタイム ライブラリ (CRT) の使用をサポートする ATL、およびでコンパイルされたアプリケーションの MFC [/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)です。 これにより、既存のアプリケーションも .NET Framework の機能を使用するためにこれらのライブラリを使用できます。

> [!IMPORTANT]
> **/Clr: 純粋な**と **/clr:safe**コンパイラ オプションが Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。

このサポートには、次の DLL とインポート ライブラリが含まれています。

- コンパイルする場合、Msvcmrt [d] .lib **/clr**です。 このインポート ライブラリへのリンクを混在アセンブリ。

このサポートは、関連するいくつかの利点を提供します。

- CRT および C++ 標準ライブラリは、混合コードを使用できます。 提供されている C++ 標準ライブラリ、CRT は検証不能です。最終的には、呼び出しはネイティブ コードから使用するとも同じ CRT および C++ 標準ライブラリにルーティングされます。

- 統一された例外処理、混合イメージを修正します。

- 混合イメージでの C++ の変数の静的な初期化します。

- マネージ コードで、AppDomain ごとと、プロセスごとの変数をサポートします。

- Visual Studio 2003 以前のバージョンでコンパイルされた混在モード Dll に適用されるローダー ロックに関する問題を解決します。

さらに、このサポートには、次の制限事項が表示されます。

- コンパイルされたコードの CRT DLL モデルのみがサポートされて **/clr**です。 サポートする静的な CRT ライブラリがありません。 **/clr**を構築します。

以前のバージョンで動作する保証はありません、現在のバージョンに、共通言語ランタイム (CLR) を更新してください。 CLR のバージョンではこれらの変更でビルドされたコードが実行されない 1.x です。

## <a name="see-also"></a>関連項目

- [混在 (ネイティブおよびマネージ) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)
