---
title: インポート ライブラリとエクスポート ファイルを作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLibrarianTool.ModuleDefinitionFile
- VC.Project.VCLibrarianTool.ExportNamedFunctions
- VC.Project.VCLibrarianTool.GenerateDebug
- VC.Project.VCLibrarianTool.ForceSymbolReferences
dev_langs:
- C++
helpviewer_keywords:
- OUT library manager option
- INCLUDE library manager option
- /DEF library manager option
- exporting data
- import libraries, building
- -INCLUDE library manager option
- /OUT library manager option
- DEF library manager option
- -DEF library manager option
- -OUT library manager option
- /INCLUDE library manager option
- -EXPORT library manager option
- exporting data, export (.exp) files
- /EXPORT library manager option
- EXPORT library manager option
- .lib files
- EXP files
ms.assetid: 2fe4f30a-1dd6-4b05-84b5-0752e1dee354
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 93f817aadf2de826c628a14255ae9257be2f29ba
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="building-an-import-library-and-export-file"></a>インポート ライブラリとエクスポート ファイルのビルド
ファイルをエクスポート、インポート ライブラリをビルドしてには次の構文を使用します。  
  
```  
LIB /DEF[:deffile] [options] [objfiles] [libraries]  
```  
  
 /DEF を指定すると、LIB LIB コマンドに渡されるエクスポート仕様からの出力ファイルを作成します。 使用の推奨される順序で一覧表示、エクスポートを指定するための 3 つの方法はあります。  
  
1.  A**方式**内のいずれかの定義、 *objfiles*または*ライブラリ*  
  
2.  /EXPORT の指定:*名前*LIB のコマンド ラインで  
  
3.  定義、**エクスポート**内のステートメント、 `deffile`  
  
 これらは、エクスポート側のプログラムをリンクするときに、エクスポートの指定を使用すると同じ方法です。 プログラムでは、1 つ以上のメソッドを使用できます。 LIB のコマンドは、の部分を指定することができます (複数など*objfiles*または/EXPORT の仕様) LIB コマンドでコマンド ファイルと同様できます LINK コマンドでします。  
  
 次のオプションは、インポート ライブラリをビルドする適用し、ファイルをエクスポートします。  
  
 /入力出力:*インポート*  
 既定の出力ファイル名を上書き、*インポート*ライブラリの作成中です。 既定の名前は、最初のオブジェクト ファイルまたはライブラリ LIB コマンドと、拡張機能の基本名で/OUT が指定されていない場合です。 lib です。 エクスポート ファイルがインポート ライブラリと拡張機能と同じ基本名を指定します。 exp です。  
  
 /EXPORT: *entryname*[= *internalname*] [、@ `ordinal`[、 **NONAME**] [、**データ**]  
 関数を呼び出すには、他のプログラムを許可するようにプログラムから関数をエクスポートします。 データをエクスポートすることもできます (を使用して、**データ**キーワード) です。 エクスポートは、通常、DLL に定義されます。  
  
 *Entryname*されている呼び出し元のプログラムで使用するのには、関数、またはデータ項目の名前です。 必要に応じて、指定することができます、 *internalname*既知の定義のプログラムで以外の場合は既定では、関数として*internalname*と同じ*entryname*です。 `ordinal`を指定しない場合は、1 ~ 65,535; の範囲内のエクスポート テーブルにインデックスを指定`ordinal`LIB が 1 つを割り当てます。 **NONAME**キーワード関数をエクスポート序数としてのみせず、 *entryname*です。 **データ**データのみのオブジェクトをエクスポートするキーワードを使用します。  
  
 /が含まれます。 `symbol`  
 指定されたシンボルをシンボル テーブルに追加します。 このオプションは、それ以外の場合と思われる含まれるライブラリ オブジェクトの使用を強制するのに役立ちます。  
  
 .Dll を作成する前に、準備手順で、インポート ライブラリを作成する場合を渡す必要がある同じ一連のオブジェクト ファイル、.dll を構築するときにインポート ライブラリを構築するときに渡したものとに注意してください。  
  
## <a name="see-also"></a>関連項目  
 [インポート ライブラリとエクスポート ファイル](../../build/reference/working-with-import-libraries-and-export-files.md)