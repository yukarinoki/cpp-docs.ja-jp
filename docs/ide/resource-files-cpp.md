---
title: リソース ファイル (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- resource files
- resources [C++]
- file types [C++], resource files
ms.assetid: 338a4a0f-0c62-4ef1-a34f-5d86262d93a4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0c295b9a3aa4996cdcd2afb17b5a4ff4c90c1159
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="resource-files-c"></a>リソース ファイル (C++)
リソースは、ユーザーに情報を提供するインターフェイス要素を示します。 ビットマップ、アイコン、ツールバー、およびカーソルは、すべてのリソースです。 メニューから選択 ダイアログ ボックスでデータを入力するなどの操作を実行する一部のリソースを操作できます。  
  
 参照してください[のリソースを操作](../windows/working-with-resource-files.md)詳細についてはします。  
  
|ファイル名|ディレクトリの場所|ソリューション エクスプローラーでの場所|説明|  
|---------------|------------------------|--------------------------------|-----------------|  
|*Projname*.rc|*Projname*|ソース ファイル|プロジェクトにリソース スクリプト ファイル。 リソース スクリプト ファイルには、プロジェクト、およびプロジェクト (たとえば、ツールバー、ダイアログ ボックス、または HTML) で選択されたサポートの種類に応じて、次が含まれています。<br /><br /> で既定メニュー定義します。<br />-アクセラレータ、文字列テーブルです。<br />-既定値**に関する** ダイアログ ボックス。<br />-その他のダイアログ ボックス。<br />アイコンのファイル (res\\*Projname*.ico)。<br />-バージョン情報です。<br />-ビットマップ。<br />ツールバー。<br />HTML ファイルです。<br /><br /> リソース ファイルには、Microsoft Foundation Class の標準のリソースについては、ファイル Afxres.rc が含まれています。|  
|Resource.h|*Projname*|ヘッダー ファイル|プロジェクトで使用したリソースの定義を含むリソースのヘッダー ファイル。|  
|*Projname*.rc2|*Projname*\res|ソース ファイル|プロジェクトで使用されるその他のリソースを含むスクリプト ファイル。 プロジェクトの .rc ファイルの上部にある .rc2 ファイルを含めることができます。<br /><br /> .Rc2 ファイルは、複数の異なるプロジェクトで使用されるリソースを含める場合に便利です。 さまざまなプロジェクトの複数回、同じリソースを作成する代わりに、.rc2 ファイルにし、.rc2 ファイルをメインの .rc ファイルに挿入できます。|  
|*Projname*.def|*Projname*|ソース ファイル|DLL プロジェクトのモジュール定義ファイル。 コントロールの名前と、コントロールの説明と、ランタイム ヒープのサイズを提供します。|  
|*Projname*.ico|*Projname*\res|リソース ファイル (Visual Studio)|プロジェクトまたはコントロールのアイコン ファイルです。 このアイコンは、アプリケーションが最小化したときに表示されます。 アプリケーションのでは使用も**に関する**ボックス。 既定では、MFC には、[MFC] アイコンと ATL には、[ATL] アイコンが用意されています。|  
|*Projname*Doc.ico|*Projname*\res|リソース ファイル (Visual Studio)|ドキュメント/ビュー アーキテクチャ サポートを含む MFC プロジェクトのアイコン ファイルです。|  
|Toolbar.bmp|*Projname*\res|リソース ファイル (Visual Studio)|アプリケーションまたはツール バーまたはパレット内のコントロールを表すビットマップ ファイルです。 このビットマップは、プロジェクトのリソース ファイルに含まれます。 初期のツールバーとステータス バーがで構築された、 **CMainFrame**クラスです。|  
|ribbon.mfcribbon ms|*Projname*\res|リソース ファイル (Visual Studio)|リボンのボタン、コントロール、および属性を定義する XML コードを含むリソース ファイル。 詳細については、「 [Ribbon Designer (MFC)](../mfc/ribbon-designer-mfc.md)」を参照してください。|  
  
## <a name="see-also"></a>関連項目  
 [Visual C++ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)