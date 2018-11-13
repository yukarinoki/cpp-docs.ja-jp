---
title: クラスの追加 (Visual C++)
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.classes.adding
helpviewer_keywords:
- ATL projects, adding classes
- classes [C++], creating
- classes [C++], adding
ms.assetid: c34b5f70-4e72-4faa-ba21-e2b05361c4d9
ms.openlocfilehash: 8cdc8dcc4241acb805255b6a28f1518e39f2bb75
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429381"
---
# <a name="adding-a-class-visual-c"></a>クラスの追加 (Visual C++)

Visual C++ プロジェクトでクラスを追加するには、**ソリューション エクスプローラー**でプロジェクトを右クリックし、**[追加]**、**[クラス]** の順にクリックします。 [[クラスの追加]](../ide/add-class-dialog-box.md) ダイアログ ボックスが開きます。

クラスを追加するとき、MFC または ATL に既に存在するクラスのものとは異なる名前を指定する必要があります。 いずれかのライブラリに既に存在する名前を指定すると、IDE はエラー メッセージを表示します。

プロジェクト命名規則によって既存名の使用が要求される場合、名前の 1 つ以上の大文字を小文字に (あるいは小文字を大文字に) 変更できます。C++ では大文字と小文字が区別されるためです。 たとえば、クラスに `CDocument` という名前を付けることはできませんが、`cdocument` という名前を付けることができます。

## <a name="what-kind-of-class-do-you-want-to-add"></a>どのような種類のクラスを追加しますか。

**[クラスの追加]** ダイアログ ボックスで、左のウィンドウの **[Visual C++]** ノードを展開すると、インストールされているテンプレートがいくつかのグループになって表示されます。 グループには、**CLR**、**ATL**、**MFC**、**C++** があります。 グループを選択すると、そのグループで利用できるテンプレートの一覧が真ん中のウィンドウに表示されます。 各テンプレートには、クラスに必要なファイルとソース コードが含まれています。

新しいクラスを生成するには、真ん中のウィンドウでテンプレートを選択し、**[名前]** ボックスにクラスの名前を入力し、**[追加]** をクリックします。 **クラスの追加ウィザード**が開くので、クラスのオプションを指定できます。

- MFC クラスを作成する方法の詳細については、[MFC クラス](../mfc/reference/adding-an-mfc-class.md)に関するページを参照してください。

- ATL クラスを作成する方法の詳細については、[ATL シンプル オブジェクト](../atl/reference/adding-an-atl-simple-object.md)に関するページを参照してください。

> [!NOTE]
>  **[MFC に ATL サポートを追加]** テンプレートの場合、クラスは作成されませんが、ATL を使用するようにプロジェクトが構成されます。 詳細については、[MFC プロジェクトの ATL サポート](../mfc/reference/adding-atl-support-to-your-mfc-project.md)に関するページを参照してください。

MFC、ATL、CLR を使用しない C++ クラスを作るには、インストールされているテンプレートの **C++** グループの **C++ クラス** テンプレートを使用します。 詳細については、「[一般 C++ クラスの追加](../ide/adding-a-generic-cpp-class.md)」を参照してください。

2 種類のフォームベース C++ クラスを利用できます。 最初の [CFormView クラス](../mfc/reference/cformview-class.md)では、MFC クラスが作成されます。 2 番目のクラスでは、CLR Windows フォーム クラスが作成されます。

## <a name="see-also"></a>参照

[フォーム ベースの MFC アプリケーションの作成](../mfc/reference/creating-a-forms-based-mfc-application.md)<br>
[[クラスの追加] ダイアログ ボックス](../ide/add-class-dialog-box.md)<br>
[アプリケーション ウィザードを使用したデスクトップ プロジェクトの作成](../ide/creating-desktop-projects-by-using-application-wizards.md)<br>
[コード ウィザードを使用した機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)