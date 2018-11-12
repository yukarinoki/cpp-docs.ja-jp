---
title: インターフェイスの実装 (Visual C++)
ms.date: 11/04/2016
helpviewer_keywords:
- interfaces, implementing
ms.assetid: 72f8731b-7e36-45db-8b10-7ef211a773cd
ms.openlocfilehash: 5146a8ced1b8347ea724940a7419d8d2507b5b58
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449648"
---
# <a name="implementing-an-interface-visual-c"></a>インターフェイスの実装 (Visual C++)

インターフェイスを実装するには、ATL COM アプリケーションとしてか、ATL サポートを含む MFC アプリケーションとしてプロジェクトを作成しておく必要があります。 ATL アプリケーションを作成するか、[ATL オブジェクトを MFC アプリケーションに追加して](../mfc/reference/adding-atl-support-to-your-mfc-project.md) MFC アプリケーションの ATL サポートを実装するには、[ATL プロジェクト ウィザード](../atl/reference/atl-project-wizard.md)を利用できます。

プロジェクトを作成したら、インターフェイスを実装するためには、最初に ATL オブジェクトを追加する必要があります。 ATL プロジェクトにオブジェクトを追加するウィザードの一覧が必要であれば、[ATL プロジェクトにオブジェクトとコントロールを追加する](../atl/reference/adding-objects-and-controls-to-an-atl-project.md)方法に関するページを参照してください。

> [!NOTE]
>  このウィザードは、ATL ダイアログ、ATL を使用する XML Web サービス、パフォーマンス オブジェクト、パフォーマンス カウンターに対応していません。

[ATL コントロールを追加する](../atl/reference/adding-an-atl-control.md)場合、ウィザードの [[インターフェイス]](../atl/reference/interfaces-atl-control-wizard.md) ページに表示され、atlcom.h で定義されている既定のインターフェイスを実装するかどうかを指定できます。

オブジェクトまたはコントロールを追加した後で、インターフェイス実装ウィザードを使用して、任意の利用可能なタイプ ライブラリ内にある他のインターフェイスを実装できます。

新しいインターフェイスを追加する場合は、プロジェクトの .idl ファイルにそれを手動で追加する必要があります。 詳細については、「[ATL プロジェクトでの新しいインターフェイスの追加](../atl/reference/adding-a-new-interface-in-an-atl-project.md)」を参照してください。

### <a name="to-implement-an-interface"></a>インターフェイスを実装するには

1. クラス ビューで、ATL オブジェクトのクラス名を右クリックします。

1. ショートカット メニューから **[追加]** をクリックし、**[インターフェイスの実装]** をクリックして、[インターフェイス実装ウィザード](../ide/implement-interface-wizard.md)を表示します。

1. 該当するタイプ ライブラリから実装するインターフェイスを選択し、**[完了]** をクリックします。

1. クラス ビューで、オブジェクトのベースとインターフェイス ノードを展開し、実装したインターフェイスを表示してから、インターフェイスのノードを展開して、使用可能なプロパティ、メソッド、およびイベントを表示します。

   > [!NOTE]
   > [オブジェクト ブラウザー](/visualstudio/ide/viewing-the-structure-of-code)を使用して、インターフェイスのメンバーを参照することもできます。

## <a name="see-also"></a>参照

[COM インターフェイスの作成](../ide/creating-a-com-interface-visual-cpp.md)<br>
[COM インターフェイスの編集](../ide/editing-a-com-interface.md)