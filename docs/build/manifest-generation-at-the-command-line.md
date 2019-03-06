---
title: コマンド ラインでのマニフェスト生成
ms.date: 11/04/2016
helpviewer_keywords:
- manifests [C++]
- manifest tool (mt.exe)
ms.assetid: fc2ff255-82b1-4c44-af76-8405c5850292
ms.openlocfilehash: 19673c9b8415c663462873e87535cf086987388d
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422651"
---
# <a name="manifest-generation-at-the-command-line"></a>コマンド ラインでのマニフェスト生成

Nmake または同様のツールを使用してコマンドラインからの C/C++ アプリケーションを構築する場合は、リンカーがすべてのオブジェクト ファイルを処理して、最終的なバイナリをビルドした後に、マニフェストが生成されます。 リンカーは、オブジェクト ファイルに格納されているアセンブリの情報を収集し、最終的なマニフェスト ファイルには、この情報を結合します。 既定では、リンカーは、という名前のファイルを生成*binary_name*.*拡張機能*.manifest が最終的なバイナリをについて説明します。 リンカーがバイナリ内のマニフェスト ファイルが埋め込まれません、のみを外部ファイルとしてマニフェストを生成できます。 いくつかの方法を使用するなど、最終的なバイナリ内のマニフェストを埋め込むには、[マニフェスト ツール (mt.exe)](https://msdn.microsoft.com/library/aa375649)マニフェストをリソース ファイルにコンパイルしたりします。 特定の規則に従う必要は、インクリメンタル リンクなどの機能を有効にする最終的なバイナリ内のマニフェストを埋め込むときに、署名に注意してくださいし、編集、続行に重要です。 これらおよびその他のオプションは、後ほど[方法。埋め込みマニフェスト内で、C/C++ アプリケーションを](../build/how-to-embed-a-manifest-inside-a-c-cpp-application.md)コマンドラインで作成するとき。

## <a name="see-also"></a>関連項目

[マニフェスト](/windows/desktop/sbscs/manifests)<br/>
[/INCREMENTAL (インクリメンタル リンクを行う)](../build/reference/incremental-link-incrementally.md)<br/>
[厳密名アセンブリ (アセンブリ署名) (C++/CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)<br/>
[エディット コンティニュ](/visualstudio/debugger/edit-and-continue)<br/>
[C/C++ プログラムのマニフェスト生成についての理解](../build/understanding-manifest-generation-for-c-cpp-programs.md)<br/>
