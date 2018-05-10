---
title: '[HLSL] プロパティ ページ: 出力ファイル |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.FXCompilerTool.AssemblerOutput
- VC.Project.FXCompilerTool.ObjectFileOutput
- VC.Project.FXCompilerTool.HeaderFileOutput
- VC.Project.FXCompilerTool.VariableName
- VC.Project.FXCompilerTool.AssemblerOutputFile
dev_langs:
- C++
ms.assetid: c5ba1e72-30de-43eb-a15a-5b0ae58e55c2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4fd1dc3ba92201567f24aa84ff8dddcd96798b38
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="hlsl-property-pages-output-files"></a>[HLSL] プロパティ ページ: 出力ファイル
HLSL コンパイラ (fxc.exe) の次のプロパティを構成するのには、使用、**出力ファイル**プロパティです。 アクセスする方法については、**出力ファイル**HLSL フォルダー内のプロパティ ページを参照してください[のプロジェクト プロパティの操作](../ide/working-with-project-properties.md)です。  
  
## <a name="uielement-list"></a>UIElement の一覧  
 **ヘッダー変数の名前**  
 HLSL オブジェクト コードのエンコードに使用される配列の名前を指定します。 配列は、HLSL コンパイラによって出力されるヘッダー ファイルに含まれます。 指定されたヘッダー ファイルの名前、**ヘッダー ファイルの名前**プロパティです。  
  
 このプロパティに対応、 **/Vn [名前]** コマンドライン引数。  
  
 **ヘッダー ファイルの名前**  
 HLSL コンパイラによって出力されるヘッダー ファイルの名前を指定します。 ヘッダーには、配列にエンコードされた HLSL オブジェクト コードが含まれています。 指定された配列の名前、**ヘッダー変数の名前**プロパティです。  
  
 このプロパティに対応、 **/Fh [名前]** コマンドライン引数。  
  
 **オブジェクト ファイルの名前**  
 HLSL コンパイラによって出力されるオブジェクト ファイルの名前を指定します。 値は、既定では、 **$(OutDir) % (Filename) .cso**です。  
  
 このプロパティに対応、 **/Fo [名前]** コマンドライン引数。  
  
 **アセンブリの出力**  
 **アセンブリのみのリスティング (/Fc)** アセンブリ言語のステートメントだけを出力します。 **アセンブリ コードと 16 進数 (/Fx)** アセンブリ言語のステートメントと、対応するオペコード 16 進数の両方を出力します。 既定では、一覧には出力はありません。  
  
 **アセンブラーの出力ファイル**  
 HLSL コンパイラによって出力されるアセンブリ リスト ファイルの名前を指定します。  
  
 このプロパティに対応、 **/Fc [name]** と **/Fx [name]** コマンドライン引数。  
  
## <a name="see-also"></a>関連項目  
 [[HLSL] プロパティ ページ](../ide/hlsl-property-pages.md)   
 [[HLSL] プロパティ ページ: 全般](../ide/hlsl-property-pages-general.md)   
 [[詳細] ([HLSL] プロパティ ページ)](../ide/hlsl-property-pages-advanced.md)