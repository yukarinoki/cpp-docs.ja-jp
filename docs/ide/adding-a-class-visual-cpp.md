---
title: クラス (Visual C) の追加 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.classes.adding
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding classes
- classes [C++], creating
- classes [C++], adding
ms.assetid: c34b5f70-4e72-4faa-ba21-e2b05361c4d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14e16d8b5c15939adb792a96a828bafd07ba4041
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="adding-a-class-visual-c"></a>クラスの追加 (Visual C++)
Visual C プロジェクトでクラスを追加する**ソリューション エクスプ ローラー**プロジェクトを右クリックしをクリックして**追加**、クリックして**クラス**です。 開き、[クラスの追加 ダイアログ ボックス](../ide/add-class-dialog-box.md) ダイアログ ボックス。  
  
 クラスを追加する場合は、MFC または ATL に既に存在するクラスとは異なる名前を指定する必要があります。 ライブラリに既に存在する名前を指定する場合、IDE は、エラー メッセージを示します。  
  
 プロジェクトの名前付け規則では、既存の名前を使用する必要がある場合だけ変更できます、名前の文字は 1 つ以上の大文字と小文字 C は大文字小文字を区別するためです。 たとえば、クラスの名前を付けられませんが`CDocument`、」と入力`cdocument`です。  
  
## <a name="what-kind-of-class-do-you-want-to-add"></a>追加するクラスの種類  
 **クラスの追加**ダイアログ ボックスで、展開すると、 **Visual C**インストールされたテンプレートのいくつかのグループが表示される左側のウィンドウ内のノードです。 グループを含める**CLR**、 **ATL**、 **MFC**、および**C++** です。 グループを選択すると、中央のペインでそのグループ内の使用可能なテンプレートの一覧が表示されます。 各テンプレートには、ファイルとクラスに必要なソース コードが含まれています。  
  
 新しいクラスを生成する、中央のペインで、テンプレートを選択、内のクラスの名前を入力、**名前**ボックスし、をクリックして**追加**です。 開き、**クラス追加ウィザード**クラスのオプションを指定できるようにします。  
  
-   MFC クラスを作成する方法の詳細については、次を参照してください。 [MFC クラス](../mfc/reference/adding-an-mfc-class.md)です。  
  
-   ATL クラスを作成する方法の詳細については、次を参照してください。 [ATL シンプル オブジェクト](../atl/reference/adding-an-atl-simple-object.md)です。  
  
> [!NOTE]
>  テンプレート**MFC に ATL サポートを追加**クラスを作成できませんが、代わりに ATL を使用するプロジェクトを構成 詳細については、次を参照してください。 [MFC プロジェクトに ATL サポート](../mfc/reference/adding-atl-support-to-your-mfc-project.md)です。  
  
 MFC や ATL、CLR を使用しない C++ クラスを作成するを使用して、 **C++ クラス**でテンプレート、 **C++** インストールされたテンプレートのグループ化します。 詳細については、次を参照してください。[一般 C++ クラスを追加する](../ide/adding-a-generic-cpp-class.md)です。  
  
 フォーム ベースの C++ クラスの 2 つの種類ができます。 最初の 1 つ[CFormView クラス](../mfc/reference/cformview-class.md)MFC クラスを作成します。 2 番目の例では、Windows フォームの CLR クラスを作成します。  
  
## <a name="see-also"></a>関連項目  
 [フォーム ベースの MFC アプリケーションを作成します。](../mfc/reference/creating-a-forms-based-mfc-application.md)   
 [クラスのダイアログ ボックスを追加します。](../ide/add-class-dialog-box.md)   
 [アプリケーション ウィザードを使用したデスクトップ プロジェクトの作成](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [コード ウィザードによる機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)