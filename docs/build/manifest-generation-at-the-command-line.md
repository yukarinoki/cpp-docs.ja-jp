---
title: コマンドラインでのマニフェスト生成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- manifests [C++]
- manifest tool (mt.exe)
ms.assetid: fc2ff255-82b1-4c44-af76-8405c5850292
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7f740030e48a33284a31da4ebd46f0c4d7b6ac7e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368500"
---
# <a name="manifest-generation-at-the-command-line"></a>コマンド ラインでのマニフェスト生成
(Nmake の) または同様のツールを使用してコマンドラインからの C/C++ アプリケーションをビルドする場合は、リンカーがすべてのオブジェクト ファイルを処理して、最終的なバイナリをビルドした後に、マニフェストが生成されます。 リンカーは、オブジェクト ファイルに格納されているアセンブリ情報を収集し、最終的なマニフェスト ファイルには、この情報を結合します。 既定では、リンカーは < binary_name > というファイルを生成します。\<拡張子 > を最終的なバイナリを記述する .manifest が付いたものです。 リンカーは、マニフェスト ファイルをバイナリが埋め込まれませんやのみ外部ファイルとしてマニフェストを生成できます。 いくつかの方法を使用するなど、最終的なバイナリ内のマニフェストを埋め込むには、[マニフェスト ツール (mt.exe)](http://msdn.microsoft.com/library/aa375649)マニフェストをリソース ファイルにコンパイルしたりします。 特定の規則の署名に、インクリメンタル リンクなどの機能を有効にする最終的なバイナリ内のマニフェストの埋め込みと後にする必要があることに留意してください、エディット コンティニュに重要です。 これらおよびその他のオプションは、後ほど[する方法: マニフェスト内の C/C++ アプリケーションに埋め込む](../build/how-to-embed-a-manifest-inside-a-c-cpp-application.md)コマンドラインで作成するときにします。  
  
## <a name="see-also"></a>関連項目  
 [マニフェスト](http://msdn.microsoft.com/library/aa375365)   
 [/INCREMENTAL (インクリメンタル リンクを)](../build/reference/incremental-link-incrementally.md)   
 [厳密名アセンブリ (アセンブリ署名) (C + + CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)   
 [エディット コンティニュ](/visualstudio/debugger/edit-and-continue)   
 [C/C++ プログラムのマニフェスト生成についての理解](../build/understanding-manifest-generation-for-c-cpp-programs.md)