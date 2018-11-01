---
title: コード ウィザードを使用した、コントロールへのタイプ セーフ アクセス
ms.date: 11/04/2016
helpviewer_keywords:
- DDX (dialog data exchange), access to controls
- code wizards
- dialog boxes [MFC], access to controls
- dialog box controls [MFC], accessing
ms.assetid: b8874393-ee48-4124-8d78-e3648a7e29b9
ms.openlocfilehash: 5f0bf03adff83ef25f3537291516368151a31a03
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436290"
---
# <a name="type-safe-access-to-controls-with-code-wizards"></a>コード ウィザードを使用した、コントロールへのタイプ セーフ アクセス

DDX の機能に慣れている場合でコントロール プロパティを使用することができます、[追加メンバー変数のウィザード](../ide/add-member-variable-wizard.md)タイプ セーフなアクセスを作成します。 このアプローチは、コード ウィザードを使用しないコントロールを作成するよりも簡単です。

単にコントロールの値にアクセスする場合、DDX によって提供します。 コントロールの値をアクセス以上の場合は、ダイアログ クラスに適切なクラスのメンバー変数を追加するメンバー変数の追加ウィザードを使用します。 このメンバー変数をコントロール プロパティにアタッチします。

メンバー変数には、値プロパティの代わりに、コントロールのプロパティを持つことができます。 Value プロパティを指すように、コントロールから返されるデータの種類`CString`または**int**します。コントロールのプロパティにより、型がなどでは、MFC コントロール クラスのいずれかがデータ メンバーを使用してコントロールに直接アクセスする`CButton`または`CEdit`します。

> [!NOTE]
>  特定のコントロールのことができますを希望する場合があるプロパティの値と最大コントロール プロパティに 1 つのメンバー変数を持つ複数のメンバー変数。 1 つだけの MFC オブジェクトをコントロール、またはその他のウィンドウにアタッチされている複数のオブジェクトは、メッセージ マップで、あいまいさにつながるため、コントロールにマップされていることができます。

このオブジェクトを使用して、コントロール オブジェクトのメンバー関数を呼び出すことができます。 このような呼び出しでは、ダイアログ ボックスのコントロールに影響します。 たとえば、チェック ボックス コントロールの変数で表される、 *m_Checkbox*、型の`CButton`、呼び出すことができます。

[!code-cpp[NVC_MFCControlLadenDialog#52](../mfc/codesnippet/cpp/type-safe-access-to-controls-with-code-wizards_1.cpp)]

ここでは、メンバー変数*m_Checkbox*メンバー関数として同じ目的を果たします`GetMyCheckbox`に示すように[コード ウィザードなしコントロールへのタイプ セーフ アクセス](../mfc/type-safe-access-to-controls-without-code-wizards.md)します。 チェック ボックスは、自動チェック ボックスではない、ボタンがクリックされたときに、ハンドラーは BN_CLICKED コントロール通知メッセージのダイアログ クラスで必要は。

コントロールの詳細については、次を参照してください。[コントロール](../mfc/controls-mfc.md)します。

## <a name="see-also"></a>関連項目

[ダイアログ ボックスのコントロールへのタイプ セーフ アクセス](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)<br/>
[ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[コード ウィザードを使用しない、コントロールへのタイプ セーフ アクセス](../mfc/type-safe-access-to-controls-without-code-wizards.md)

