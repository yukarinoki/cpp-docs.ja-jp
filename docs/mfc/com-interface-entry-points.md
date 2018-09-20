---
title: COM インターフェイス エントリ ポイント |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- entry points, COM interfaces
- state management, OLE/COM interfaces
- MFC COM, COM interface entry points
- OLE, interface entry points
- MFC, managing state data
- COM interfaces, entry points
ms.assetid: 9e7421dc-0731-4748-9e1b-90acbaf26d77
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a955e3fc768dd7ba38ffbcf32b190a9d6038196b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46414280"
---
# <a name="com-interface-entry-points"></a>COM インターフェイスのエントリ ポイント

COM インターフェイスのメンバー関数は、使用、 [METHOD_PROLOGUE](com-interface-entry-points.md#method_prologue)エクスポートされたインターフェイスのメソッドを呼び出すときに、適切なグローバル状態を維持するためにマクロ。

によって実装されるインターフェイスのメンバー関数の通常、 `CCmdTarget`-の自動初期化を提供する、このマクロを既に使用して派生オブジェクト、`pThis`ポインター。 例えば:

[!code-cpp[NVC_MFCConnectionPoints#5](../mfc/codesnippet/cpp/com-interface-entry-points_1.cpp)]

詳細については、次を参照してください。[テクニカル ノート 38](../mfc/tn038-mfc-ole-iunknown-implementation.md) MFC/OLE で`IUnknown`実装します。

`METHOD_PROLOGUE`としてマクロが定義されます。

```cpp
#define METHOD_PROLOGUE(theClass, localClass) \
    theClass* pThis = \
    ((theClass*)((BYTE*)this - offsetof(theClass, m_x##localClass))); \
    AFX_MANAGE_STATE(pThis->m_pModuleState) \

```

マクロ、グローバル状態の管理に関連の部分は次のとおりです。

`AFX_MANAGE_STATE( pThis->m_pModuleState )`

この式で*m_pModuleState*親オブジェクトのメンバー変数と見なされます。 によって実装されている、`CCmdTarget`基底クラスとは、適切な値に初期化`COleObjectFactory`オブジェクトがインスタンス化されるときに、します。

## <a name="see-also"></a>関連項目

[MFC モジュールの状態データの管理](../mfc/managing-the-state-data-of-mfc-modules.md)

