---
title: コマンド ラインでのマニフェスト生成
ms.date: 11/04/2016
helpviewer_keywords:
- manifests [C++]
- manifest tool (mt.exe)
ms.assetid: fc2ff255-82b1-4c44-af76-8405c5850292
ms.openlocfilehash: 381406213422e286dd9aba26adcdbd6caff7bfe3
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493202"
---
# <a name="manifest-generation-at-the-command-line"></a>コマンド ラインでのマニフェスト生成

nmake または同様のツールでコマンド ラインから C/C++ アプリケーションをビルドすると、リンカーによってすべてのオブジェクト ファイルが処理され。最終バイナリがビルドされてから、マニフェストが生成されます。 リンカーによって、オブジェクト ファイルに保存されているアセンブリ情報が収集され、この情報が最終マニフェスト ファイルに結合されます。 既定では、リンカーによって、最終バイナリを説明する *binary_name*.*extension*.manifest という名前のファイルが生成されます。 リンカーによってバイナリ内にマニフェスト ファイルが埋め込まれることはありません。リンカーでは、外部ファイルとしてのみマニフェストを生成できます。 最終バイナリの中にマニフェストを埋め込む方法はいくつかあります。たとえば、[マニフェスト ツール (mt.exe)](/windows/win32/sbscs/mt-exe) を使用するか、マニフェストをリソース ファイルにコンパイルします。 これは重要なことですが、インクリメンタル リンク、署名、エディット コンティニュなどの機能を有効にするため、最終バイナリの中にマニフェストを埋め込むとき、特定の規則に従わなければならないことに注意してください。 コマンド ラインでビルドするときの規則とその他のオプションについては、「[方法:マニフェストを C/C++ アプリケーションに埋め込む](how-to-embed-a-manifest-inside-a-c-cpp-application.md)」に説明があります。

## <a name="see-also"></a>関連項目

[マニフェスト](/windows/win32/sbscs/manifests)<br/>
[/INCREMENTAL (インクリメンタル リンクを行う)](reference/incremental-link-incrementally.md)<br/>
[厳密名アセンブリ (アセンブリ署名) (C++/CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)<br/>
[エディット コンティニュ](/visualstudio/debugger/edit-and-continue)<br/>
[C/C++ プログラムのマニフェスト生成についての理解](understanding-manifest-generation-for-c-cpp-programs.md)<br/>
