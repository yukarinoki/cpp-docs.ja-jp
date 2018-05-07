---
title: XML ドキュメント (Visual C) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- XML documentation
- XML, documentation comments in source code
- comments, C++ source code files
- /// delimiter for C++ documentation
ms.assetid: a1aec1c5-b2d1-4c74-83ae-1dbbbb76b506
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9ee19c51c04fa32ab3c2f1810bb963b22ec7e890
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="xml-documentation-visual-c"></a>XML に関するドキュメント (Visual C++)
Visual c では、.xml ファイルに処理される、ソース コードにコメントを追加できます。 このファイルは、コードでクラスのドキュメントを作成するプロセスへの入力にできます。  
  
 Visual C のコード ファイルで XML ドキュメント コメントは、メソッドまたは型の定義より前に直接配置する必要があります。 コメントは、次のシナリオでの Intellisense のクイック ヒント データのヒントの設定を使用できます。  
  
1.  Windows ランタイム コンポーネント、付随する .winmd ファイルと共にそのコードがコンパイルされるときに  
  
2.  現在のプロジェクトで、ソース コードが含まれている場合  
  
3.  ライブラリ内の型の宣言および実装内にある、同じヘッダー ファイル  
  
> [!NOTE]
>  現在のリリースでは、テンプレートまたはテンプレートの種類 (たとえば、テンプレートとしてパラメーターを取り込む関数) が格納されているコードのコメントは処理されません。 このようなコメントを追加すると、未定義の動作が発生します。  
  
 ドキュメント コメントで、.xml ファイルを作成する方法の詳細については、次のトピックを参照してください。  
  
|参照する内容|解決方法については、|  
|---------------------------|---------|  
|使用するコンパイラ オプション|[/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)|  
|一般提供に使用できるタグのドキュメントの機能を使用します。|[ドキュメント コメントとして推奨されるタグ](../ide/recommended-tags-for-documentation-comments-visual-cpp.md)|  
|コンパイラは、コード内の構成体を識別する生成 ID の文字列|[.Xml ファイルの処理](../ide/dot-xml-file-processing.md)|  
|ドキュメント タグの区切り方法|[Visual C++ ドキュメント タグの区切り記号](../ide/delimiters-for-visual-cpp-documentation-tags.md)|  
|1 つまたは複数の .xdc ファイルから .xml ファイルを生成しています。|[XDCMake リファレンス](../ide/xdcmake-reference.md)|  
|Visual Studio の機能領域に関連している XML に関する情報へのリンク|[Visual Studio での XML](/visualstudio/xml-tools/xml-tools-in-visual-studio)|  
  
 ドキュメント コメントのテキストの XML 特殊文字を配置する必要がある場合は、XML エンティティ内または CDATA セクションを使用する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)