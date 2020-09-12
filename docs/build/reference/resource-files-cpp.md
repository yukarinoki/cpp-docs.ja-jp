---
title: プロジェクトリソースファイル (C++)
ms.date: 05/14/2019
helpviewer_keywords:
- resource files
- resources [C++]
ms.assetid: 338a4a0f-0c62-4ef1-a34f-5d86262d93a4
ms.openlocfilehash: d37c3602d8939db609fc8af42dd764655195b24b
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041017"
---
# <a name="project-resource-files-c"></a>プロジェクトリソースファイル (C++)

リソースは、ユーザーに情報を提供するインターフェイス要素です。 ビットマップ、アイコン、ツールバー、カーソルはすべてリソースです。 一部のリソースでは、メニューから選択したり、ダイアログ ボックスにデータを入力したりするなどの操作を実行できます。

詳細については、[リソースの操作](../../windows/working-with-resource-files.md)に関するページをご覧ください。

|ファイル名|ディレクトリの場所|ソリューション エクスプローラーでの場所|説明|
|---------------|------------------------|--------------------------------|-----------------|
|*Projname*.rc|*Projname*|ソース ファイル|プロジェクトのリソース スクリプト ファイル。 リソース スクリプト ファイルには、プロジェクトの種類に応じて次が含まれています。また、プロジェクトに対して選択されているサポートが含まれています (ツール バー、ダイアログ ボックス、HTML など)。<br /><br />- 既定のメニュー定義。<br />- アクセラレータと文字列テーブル。<br />-既定の [ **バージョン情報** ] ダイアログボックス。<br />- その他のダイアログ ボックス。<br />-アイコンファイル (res \\ *の*.ico)。<br />- バージョン情報。<br />- ビットマップ。<br />- ツール バー。<br />- HTML ファイル。<br /><br /> リソース ファイルには、標準 Microsoft Foundation Class リソースのファイル Afxres.rc が含まれています。|
|Resource.h|*Projname*|ヘッダー ファイル|プロジェクトによって使用されるリソースの定義を含むリソース ヘッダー ファイル。|
|*Projname*.rc2|*Projname*\res|ソース ファイル|プロジェクトによって使用される追加リソースを含むスクリプト ファイル。 プロジェクトの .rc ファイルの下に .rc2 ファイルを含めることができます。<br /><br /> .rc2 ファイルは、いくつかの異なるプロジェクトによって使用されるリソースを含めるときに便利です。 異なるプロジェクトに対して同じリソースを複数回作成しなくても、1 つの .rc2 ファイルに入れ、その .rc2 ファイルをメインの .rc ファイルに含めます。|
|*Projname*.def|*Projname*|ソース ファイル|DLL プロジェクトのモジュール定義ファイル。 コントロールの場合、ランタイム ヒープのサイズに加え、コントロールの名前と説明が提供されます。|
|*Projname*.ico|*Projname*\res|リソース ファイル (Visual Studio)|プロジェクトまたはコントロールのアイコン ファイル。 このアイコンは、アプリケーションが最小化されると表示されます。 アプリケーションの **[バージョン情報]** ボックスでも使用されます。 既定では、MFC で MFC アイコンが、ATL で ATL アイコンが与えられます。|
|*Projname*Doc.ico|*Projname*\res|リソース ファイル (Visual Studio)|ドキュメント/ビュー アーキテクチャのサポートが含まれる MFC プロジェクトのアイコン ファイル。|
|Toolbar.bmp|*Projname*\res|リソース ファイル (Visual Studio)|ツール バーまたはパレットでアプリケーションまたはコントロールを表すビットマップ ファイル。 このビットマップは、プロジェクトのリソース ファイルに含まれます。 最初のツール バーとステータス バーは **CMainFrame** クラスで構築されます。|
|ribbon.mfcribbon-ms|*Projname*\res|リソース ファイル (Visual Studio)|リボンのボタン、コントロール、属性を定義する XML コードを含むリソース ファイル。 詳細については、「 [Ribbon Designer (MFC)](../../mfc/ribbon-designer-mfc.md)」を参照してください。|

## <a name="see-also"></a>参照

[Visual Studio の C++ プロジェクトに対して作成されるファイルの種類](file-types-created-for-visual-cpp-projects.md)
