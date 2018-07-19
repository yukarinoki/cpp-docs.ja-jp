---
title: スピン ボタンのメンバー関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- spin button control, methods
- CSpinButtonCtrl class [MFC], methods
ms.assetid: a08a26fd-b803-4cbe-a509-395fa357d057
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 524863b816c62903cb610b57a6e3275bcdf6a3d6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33381252"
---
# <a name="spin-button-member-functions"></a>スピン ボタンのメンバー関数
いくつかのメンバー関数は、スピン コントロールの使用可能な ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md))。 スピン ボタンの次の属性を変更するのにには、これらの関数を使用します。  
  
-   **アクセラレータ**矢印ボタンを押したときに、位置が変化率を調整することができます。 アクセラレータを使用するを使用して、 [SetAccel](../mfc/reference/cspinbuttonctrl-class.md#setaccel)と[GetAccel](../mfc/reference/cspinbuttonctrl-class.md#getaccel)メンバー関数。  
  
-   **基本**が連動ウィンドウのキャプションの位置を表示するために使用ベース (10 または 16) を変更することができます。 使用して、ベースを使用する、 [GetBase](../mfc/reference/cspinbuttonctrl-class.md#getbase)と[SetBase](../mfc/reference/cspinbuttonctrl-class.md#setbase)メンバー関数。  
  
-   **ウィンドウを友人**が連動ウィンドウを動的に設定することができます。 使用してクエリを実行したり、どのコントロールが連動ウィンドウを変更したり、 [GetBuddy](../mfc/reference/cspinbuttonctrl-class.md#getbuddy)と[SetBuddy](../mfc/reference/cspinbuttonctrl-class.md#setbuddy)メンバー関数。  
  
-   **位置**クエリし、位置を変更することができます。 位置を直接操作するには、使用、 [GetPos](../mfc/reference/cspinbuttonctrl-class.md#getpos)と[SetPos](../mfc/reference/cspinbuttonctrl-class.md#setpos)メンバー関数。 (たとえば、に備えて、友人がエディット コントロールである)、アップダウン コントロールのキャプションが変更されたため`GetPos`現在のキャプションを取得し、それに応じて位置を調整します。  
  
-   **範囲**スピン ボタンの最大値と最小の位置を変更することができます。 既定では、最大値は 0 に設定し、最小値は 100 に設定します。 既定の最大値は、既定の最小値未満であるため、矢印ボタンの動作は逆です。 通常は設定を使用して、範囲、 [SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange)メンバー関数。 範囲を使用するクエリを実行する[GetRange](../mfc/reference/cspinbuttonctrl-class.md#getrange)です。  
  
## <a name="see-also"></a>関連項目  
 [CSpinButtonCtrl の使い方](../mfc/using-cspinbuttonctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

