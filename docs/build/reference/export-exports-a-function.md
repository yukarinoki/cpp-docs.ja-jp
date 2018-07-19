---
title: -エクスポート (関数のエクスポート) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.ExportFunctions
- /export
dev_langs:
- C++
helpviewer_keywords:
- /EXPORT linker option
- EXPORT linker option
- -EXPORT linker option
ms.assetid: 0920fb44-a472-4091-a8e6-73051f494ca0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f366b40e8e40e62f67ec45f3e59ad61eb338c427
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374493"
---
# <a name="export-exports-a-function"></a>/EXPORT (関数のエクスポート)
```  
/EXPORT:entryname[,@ordinal[,NONAME]][,DATA]  
```  
  
## <a name="remarks"></a>コメント  
 このオプションを使用して他のプログラムには、この関数を呼び出すようにに、プログラムから関数をエクスポートできます。 データをエクスポートすることもできます。 エクスポートは、通常、DLL に定義されます。  
  
 *Entryname*されている呼び出し元のプログラムで使用するのには、関数、またはデータ項目の名前です。 `ordinal` 1 ~ 65,535; の範囲内で、エクスポート テーブルにインデックスを指定します。指定しない場合`ordinal`、いずれかのリンクが割り当てられます。 **NONAME**キーワード関数をエクスポート序数としてのみせず、 *entryname*です。  
  
 **データ**キーワードは、エクスポートされた項目がデータ項目を指定します。 クライアント プログラムでデータ項目を使用して宣言する必要があります**extern _declspec**です。  
  
 使用の推奨される順序で、定義をエクスポートするための 3 つの方法はあります。  
  
1.  [方式](../../cpp/dllexport-dllimport.md)のソース コードで  
  
2.  [エクスポート](../../build/reference/exports.md).def ファイル内のステートメント  
  
3.  LINK コマンドで、/EXPORT 仕様  
  
 3 つのメソッドは、同じプログラムで使用できます。 リンクは、エクスポートを含むプログラムをビルドも作成、インポート ライブラリ ビルドで .exp ファイルを使用しない限り、します。  
  
 リンクは、装飾された識別子の形式です。 コンパイラは、.obj ファイルの作成時に、識別子を修飾します。 場合*entryname*装飾されていないはリンカーに指定された形式 (ソース コードが表示されます)、リンクは、名前を照合しようとしています。 一意の一致が見つからない場合、リンクは、エラー メッセージを発行します。 使用して、 [DUMPBIN](../../build/reference/dumpbin-reference.md)を取得するツール、[装飾名](../../build/reference/decorated-names.md)リンカーに指定する必要がある場合、識別子の形式です。  
  
> [!NOTE]
>  宣言されている C 識別子の装飾形式を指定しない`__cdecl`または`__stdcall`です。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  **[コマンド ライン]** プロパティ ページをクリックします。  
  
4.  オプションを入力、**追加オプション**ボックス。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)