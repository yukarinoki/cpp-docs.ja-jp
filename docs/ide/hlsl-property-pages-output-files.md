---
title: '[HLSL] プロパティ ページ: 出力ファイル | Microsoft Docs'
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
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "33339197"
---
# <a name="hlsl-property-pages-output-files"></a>[HLSL] プロパティ ページ: 出力ファイル
HLSL コンパイラ (fxc.exe) の次のプロパティを構成するには、その **[出力ファイル]** プロパティを使用します。 HLSL フォルダーの **[出力ファイル]** プロパティにアクセスする方法については、「[プロジェクト プロパティの操作](../ide/working-with-project-properties.md)」を参照してください。  
  
## <a name="uielement-list"></a>UIElement の一覧  
 **ヘッダー変数名**  
 エンコードされた HLSL オブジェクト コードに使用される配列の名前を指定します。 この配列は、HLSL コンパイラによって出力されるヘッダー ファイルに含まれます。 ヘッダー ファイルの名前は、**ヘッダー ファイル名**プロパティで指定されます。  
  
 このプロパティは、**/Vn[name]** コマンドライン引数に対応します。  
  
 **ヘッダー ファイル名**  
 HLSL コンパイラによって出力されるヘッダー ファイルの名前を指定します。 ヘッダーには、配列にエンコードされた HLSL オブジェクト コードが含まれています。 配列の名前は、**ヘッダー変数名**プロパティで指定されます。  
  
 このプロパティは、**/Fh[name]** コマンドライン引数に対応します。  
  
 **オブジェクト ファイル名**  
 HLSL コンパイラによって出力されるオブジェクト ファイルの名前を指定します。 既定では、値は **$(OutDir)%(Filename).cso** です。  
  
 このプロパティは、**/Fo[name]** コマンドライン引数に対応します。  
  
 **アセンブラー出力**  
 アセンブリ言語のステートメントだけを出力する**アセンブリ コードのみ (/Fc)**。 アセンブリ言語ステートメントと、対応するオペコードの両方を 16 進数で出力する**アセンブリ コードと 16 進数 (/Fx)**。 既定では、リストは出力されません。  
  
 **アセンブラー出力ファイル**  
 HLSL コンパイラによって出力されるアセンブリ リスト ファイルの名前を指定します。  
  
 このプロパティは、**/Fo[name]** と **/Fx [name]** のコマンドライン引数に対応します。  
  
## <a name="see-also"></a>参照  
 [[HLSL] プロパティ ページ](../ide/hlsl-property-pages.md)   
 [[全般] ([HLSL] プロパティ ページ)](../ide/hlsl-property-pages-general.md)   
 [[詳細] ([HLSL] プロパティ ページ)](../ide/hlsl-property-pages-advanced.md)