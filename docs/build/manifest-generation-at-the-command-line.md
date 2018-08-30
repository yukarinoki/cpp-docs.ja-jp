---
title: コマンドラインでのマニフェスト生成 |Microsoft Docs
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
ms.openlocfilehash: 97e2bb423deb4a50da0cf0772ae81e19bb4b48eb
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43220728"
---
# <a name="manifest-generation-at-the-command-line"></a>コマンド ラインでのマニフェスト生成
Nmake または同様のツールを使用してコマンドラインからの C/C++ アプリケーションを構築する場合は、リンカーがすべてのオブジェクト ファイルを処理して、最終的なバイナリをビルドした後に、マニフェストが生成されます。 リンカーは、オブジェクト ファイルに格納されているアセンブリの情報を収集し、最終的なマニフェスト ファイルには、この情報を結合します。 既定では、リンカーは < binary_name > という名前のファイルを生成します。\<拡張機能 > .manifest が最終的なバイナリをについて説明します。 リンカーがバイナリ内のマニフェスト ファイルが埋め込まれません、のみを外部ファイルとしてマニフェストを生成できます。 いくつかの方法を使用するなど、最終的なバイナリ内のマニフェストを埋め込むには、[マニフェスト ツール (mt.exe)](https://msdn.microsoft.com/library/aa375649)マニフェストをリソース ファイルにコンパイルしたりします。 特定の規則に従う必要は、インクリメンタル リンクなどの機能を有効にする最終的なバイナリ内のマニフェストを埋め込むときに、署名に注意してくださいし、編集、続行に重要です。 これらおよびその他のオプションは、後ほど[方法: 埋め込みマニフェスト内で、C/C++ アプリケーションを](../build/how-to-embed-a-manifest-inside-a-c-cpp-application.md)コマンドラインで作成するとき。  
  
## <a name="see-also"></a>関連項目  
 [マニフェスト](https://msdn.microsoft.com/library/aa375365)   
 [/INCREMENTAL (インクリメンタル リンクを)](../build/reference/incremental-link-incrementally.md)   
 [厳密名アセンブリ (アセンブリ署名) (C +/cli CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)   
 [エディット コンティニュ](/visualstudio/debugger/edit-and-continue)   
 [C/C++ プログラムのマニフェスト生成についての理解](../build/understanding-manifest-generation-for-c-cpp-programs.md)