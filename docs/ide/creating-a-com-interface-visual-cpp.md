---
title: COM インターフェイスの作成 (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.com.creating.interfaces
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, creating
ms.assetid: 1be84d3c-6886-4d1e-8493-56c4d38a96d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e573e65e1b9f3638aaa2f1b25c36d6c959f194d8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46390100"
---
# <a name="creating-a-com-interface-visual-c"></a>COM インターフェイスの作成 (Visual C++)

Visual C++ には、COM オブジェクトとオートメーション クラスのインターフェイスとディスパッチ インターフェイスを定義する COM を使用するプロジェクトを作成するためのウィザードとテンプレートが用意されています。

これらのウィザードを使用して、次の 3 つの一般的なタスクを実行できます。

- [MFC プロジェクトへの ATL サポートの追加](../mfc/reference/adding-atl-support-to-your-mfc-project.md)

   [MFC アプリケーション ウィザード](../mfc/reference/mfc-application-wizard.md)を使用して MFC プロジェクトを作成し、**MFC に ATL サポートを追加**コード ウィザードを実行した後で、MFC アプリケーションに ATL サポートを追加します。 このサポートは、MFC の実行可能ファイルまたは DLL プロジェクトに追加された単純な COM オブジェクトにのみ適用されます。 これらの ATL オブジェクトでは、複数のインターフェイスがあります。

- [MFC ActiveX コントロールの作成](../mfc/reference/creating-an-mfc-activex-control.md)

   [MFC ActiveX コントロール ウィザード](../mfc/reference/mfc-activex-control-wizard.md)を開き、それぞれ、.idl ファイルとコントロール クラスで定義されているディスパッチ インターフェイスとイベント マップを含む ActiveX コントロールを作成します。

- [ATL コントロールの追加](../atl/reference/adding-an-atl-control.md)

   [ATL プロジェクト ウィザード](../atl/reference/atl-project-wizard.md)と [ATL コントロール ウィザード](../atl/reference/atl-control-wizard.md)の組み合わせを使用して、ATL ActiveX コントロールを作成します。

   前述のとおり、ATL サポートを追加した MFC プロジェクトに ATL コントロールを追加することもできます。 さらに、**[クラスの追加]** ダイアログ ボックスで、**ATL コントロール**を選択し、ATL サポートを MFC プロジェクトに追加していない場合、Visual Studio で ATL サポートを MFC プロジェクトに追加することを確認するダイアログ ボックスが表示されます。

   このウィザードは、プロジェクト クラスに IDL ソースと COM マップを生成します。

ATL プロジェクトが開いたら、[[クラスの追加]](../ide/add-class-dialog-box.md) ダイアログ ボックスで、COM インターフェイスをプロジェクトに追加するための追加のウィザードおよびテンプレートを選択できます。 次のウィザードでは、オブジェクトの 1 つまたは複数のインターフェイスを確立できます。

- [ATL COM+ 1.0 コンポーネント ウィザード](../atl/reference/atl-com-plus-1-0-component-wizard.md)

- [ATL シンプル オブジェクト ウィザード](../atl/reference/atl-simple-object-wizard.md)

- [ATL Active Server Page コンポーネント ウィザード](../atl/reference/atl-active-server-page-component-wizard.md)

- [ATL コントロール ウィザード](../atl/reference/atl-control-wizard.md)

さらに、クラス ビューでオブジェクトのコントロール クラスを右クリックし、[[インターフェイスの実装]](../ide/implement-interface-wizard.md) をクリックすることで、COM コントロールに新しいインターフェイスを実装できます。

> [!NOTE]
>  Visual Studio では、インターフェイスをプロジェクトに追加するウィザードは提供されません。 [ATL シンプル オブジェクト ウィザード](../atl/reference/atl-simple-object-wizard.md)を使用してシンプル オブジェクトを追加することで、インターフェイスを ALT プロジェクトに追加するか、[MFC プロジェクトに ATL サポートを追加](../mfc/reference/adding-atl-support-to-your-mfc-project.md)できます。 また、プロジェクトの .idl ファイルを開き、次のように入力してインターフェイスを作成することもできます。

```
interface IMyInterface {
};

```

詳細については、「[インターフェイスの実装](../ide/implementing-an-interface-visual-cpp.md)」および「[Adding Objects and Controls to an ATL Project](../atl/reference/adding-objects-and-controls-to-an-atl-project.md)」 (ALT プロジェクトへのオブジェクトとコントロールの追加) を参照してください。

Visual C++ では、いくつかの方法を使用して、プロジェクトに対して定義された [COM インターフェイスを表示および編集](../ide/editing-a-com-interface.md)できます。 [クラス ビュー](/visualstudio/ide/viewing-the-structure-of-code)には、C++ プロジェクトの .idl ファイルで定義されている任意のインターフェイスまたはディスパッチ インターフェイスのアイコンが表示されます。

ATL ベースの COM オブジェクト クラスの場合、クラス ビューは、ATL クラスの COM マップを読み込み、ATL クラスとそれが実装するインターフェイスの間の関係を表示します。

クラス ビューおよびそのショートカット メニューで、インターフェイスを次のように操作できます。

- ATL オブジェクトを MFC ベースのアプリケーションに追加します。

- メソッド、プロパティ、およびイベントを追加します。

- アイテムをダブルクリックして、アイテムのインターフェイス コードに直接ジャンプします。

## <a name="see-also"></a>参照

[アプリケーション ウィザードを使用したデスクトップ プロジェクトの作成](../ide/creating-desktop-projects-by-using-application-wizards.md)<br>
[コード ウィザードを使用した機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)