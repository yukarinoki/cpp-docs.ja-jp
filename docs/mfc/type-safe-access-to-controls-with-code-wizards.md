---
title: コード ウィザードを使用した、コントロールへのタイプ セーフ アクセス
ms.date: 11/04/2016
helpviewer_keywords:
- DDX (dialog data exchange), access to controls
- code wizards
- dialog boxes [MFC], access to controls
- dialog box controls [MFC], accessing
ms.assetid: b8874393-ee48-4124-8d78-e3648a7e29b9
ms.openlocfilehash: b49c1b6f21dfe5270e40649241812320303ad411
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370917"
---
# <a name="type-safe-access-to-controls-with-code-wizards"></a>コード ウィザードを使用した、コントロールへのタイプ セーフ アクセス

DDX 機能に精通している場合は、[メンバー変数の追加ウィザード](../ide/add-member-variable-wizard.md)の Control プロパティを使用して、タイプ セーフなアクセスを作成できます。 この方法は、コード ウィザードを使用せずにコントロールを作成するよりも簡単です。

コントロールの値にアクセスするだけの場合は、DDX がコントロールの値を提供します。 コントロールの値にアクセスする以外の操作を行う場合は、メンバー変数の追加ウィザードを使用して、適切なクラスのメンバー変数をダイアログ クラスに追加します。 このメンバー変数を Control プロパティにアタッチします。

メンバー変数は、Value プロパティの代わりに Control プロパティを持つことができます。 Value プロパティは、コントロールから返されるデータの型`CString`を参照**します**。Control プロパティを使用すると、型が MFC のコントロール クラスの 1 つであるデータ メンバーを介`CButton`して`CEdit`コントロールに直接アクセスできます。

> [!NOTE]
> コントロールに対して、必要に応じて、Value プロパティを持つ複数のメンバー変数を持ち、Control プロパティを持つメンバー変数を 1 つ以上持つことができます。 コントロールまたは他のウィンドウにアタッチされた複数のオブジェクトがメッセージ マップであいまいになるため、MFC オブジェクトをコントロールにマップできるのは 1 つだけです。

このオブジェクトを使用して、コントロール オブジェクトの任意のメンバー関数を呼び出すことができます。 このような呼び出しは、ダイアログ ボックスのコントロールに影響します。 たとえば、 の変数*m_Checkbox*で表されるチェック ボックス コントロールの`CButton`場合は、次のように呼び出します。

[!code-cpp[NVC_MFCControlLadenDialog#52](../mfc/codesnippet/cpp/type-safe-access-to-controls-with-code-wizards_1.cpp)]

ここでは、メンバー変数*m_Checkbox*は、「[コード ウィザードを使用しないコントロールへのタイプ セーフ アクセス](../mfc/type-safe-access-to-controls-without-code-wizards.md)」に示すメンバー関数`GetMyCheckbox`と同じ目的で使用できます。 チェック ボックスが自動チェック ボックスでない場合は、ボタンがクリックされたときに、BN_CLICKEDのコントロール通知メッセージのダイアログ クラスにハンドラーが必要です。

コントロールの詳細については、「[コントロール](../mfc/controls-mfc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ダイアログ ボックス内のコントロールへのタイプ セーフ アクセス](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)<br/>
[MFC でのダイアログ ボックスの操作](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[コード ウィザードを使用しない、コントロールへのタイプ セーフ アクセス](../mfc/type-safe-access-to-controls-without-code-wizards.md)
