---
title: コード ウィザードを使用したコントロールにタイプ セーフ アクセス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DDX (dialog data exchange), access to controls
- code wizards
- dialog boxes [MFC], access to controls
- dialog box controls [MFC], accessing
ms.assetid: b8874393-ee48-4124-8d78-e3648a7e29b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 88f86a8f22bae990261be5150755a26d50d4bef8
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950462"
---
# <a name="type-safe-access-to-controls-with-code-wizards"></a>コード ウィザードを使用した、コントロールへのタイプ セーフ アクセス
DDX 機能を使い慣れている場合でコントロール プロパティを使用することができます、[変数の追加メンバー ウィザード](../ide/add-member-variable-wizard.md): タイプ セーフなアクセスを作成します。 この方法は、コード ウィザードを使用しないコントロールを作成するよりも簡単です。  
  
 単純にする場合、コントロールの値へのアクセス、DDX を使用してください。 複数のコントロールの値にアクセスする場合は、メンバー変数の追加ウィザードを使用して、ダイアログ クラスに、適切なクラスのメンバー変数を追加します。 このメンバー変数をコントロールのプロパティにアタッチします。  
  
 メンバー変数は、値のプロパティではなく、コントロール プロパティを持つことができます。 Value プロパティを指すように、コントロールから返されるデータの種類`CString`または**int**です。コントロールのプロパティを使用して、データ型を持つメンバー MFC では、コントロール クラスのいずれかなどを使用してコントロールに直接アクセスする`CButton`または`CEdit`です。  
  
> [!NOTE]
>  特定のコントロールでのする場合は、したプロパティの値と最大でコントロールのプロパティを持つ 1 つのメンバー変数を持つ複数のメンバー変数できます。 1 つだけの MFC オブジェクトがコントロール、またはその他のウィンドウにアタッチされている複数のオブジェクトは、メッセージ マップのあいまいさにつながるために、コントロールにマップされていることができます。  
  
 このオブジェクトを使用して、コントロール オブジェクトのメンバー関数を呼び出すことができます。 このような呼び出しでは、ダイアログ ボックスのコントロールに影響します。 たとえば、チェック ボックス コントロールの変数で表された、 *m_Checkbox*、型の`CButton`、呼び出す可能性があります。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#52](../mfc/codesnippet/cpp/type-safe-access-to-controls-with-code-wizards_1.cpp)]  
  
 ここでは、メンバー変数*m_Checkbox*メンバー関数として同じ目的を果たします`GetMyCheckbox`に示すように[コード ウィザードなしのコントロールへのタイプ セーフ アクセス](../mfc/type-safe-access-to-controls-without-code-wizards.md)です。 チェック ボックスは、自動チェック ボックスではない、ボタンがクリックされたときのハンドラーは BN_CLICKED コントロール通知メッセージのダイアログ クラスで必要なります。  
  
 コントロールの詳細については、次を参照してください。[コントロール](../mfc/controls-mfc.md)です。  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックスのコントロールへのタイプ セーフ アクセス](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)   
 [ダイアログ ボックスのライフ サイクル](../mfc/life-cycle-of-a-dialog-box.md)   
 [コード ウィザードを使用しない、コントロールへのタイプ セーフ アクセス](../mfc/type-safe-access-to-controls-without-code-wizards.md)

