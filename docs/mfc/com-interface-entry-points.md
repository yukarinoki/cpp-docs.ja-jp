---
description: 詳細については、「COM インターフェイスのエントリポイント」を参照してください。
title: COM インターフェイスのエントリ ポイント
ms.date: 03/27/2019
helpviewer_keywords:
- entry points, COM interfaces
- state management, OLE/COM interfaces
- MFC COM, COM interface entry points
- OLE, interface entry points
- MFC, managing state data
- COM interfaces, entry points
ms.assetid: 9e7421dc-0731-4748-9e1b-90acbaf26d77
ms.openlocfilehash: 805ac906c3ccca246d1af71c689aaf768f789999
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160013"
---
# <a name="com-interface-entry-points"></a>COM インターフェイスのエントリ ポイント

COM インターフェイスのメンバー関数の場合は、エクスポートされたインターフェイスのメソッドを呼び出すときに、マクロを使用して、 `METHOD_PROLOGUE` 適切なグローバル状態を維持します。

通常、派生オブジェクトによって実装されたインターフェイスのメンバー関数は、 `CCmdTarget` このマクロを使用してポインターを自動的に初期化し `pThis` ます。 次に例を示します。

[!code-cpp[NVC_MFCConnectionPoints#5](codesnippet/cpp/com-interface-entry-points_1.cpp)]

詳細については、「MFC/OLE の実装に関する [テクニカルノート 38](tn038-mfc-ole-iunknown-implementation.md) 」を参照してください `IUnknown` 。

`METHOD_PROLOGUE`マクロは次のように定義されます。

```cpp
#define METHOD_PROLOGUE(theClass, localClass) \
    theClass* pThis = \
    ((theClass*)((BYTE*)this - offsetof(theClass, m_x##localClass))); \
    AFX_MANAGE_STATE(pThis->m_pModuleState) \
```

グローバル状態の管理に関係するマクロの部分は次のとおりです。

`AFX_MANAGE_STATE( pThis->m_pModuleState )`

この式では、 *m_pModuleState* は、含んでいるオブジェクトのメンバー変数であると見なされます。 これは基底クラスによって実装され、 `CCmdTarget` `COleObjectFactory` オブジェクトがインスタンス化されるときに、によって適切な値に初期化されます。

## <a name="see-also"></a>関連項目

[MFC モジュールの状態データの管理](managing-the-state-data-of-mfc-modules.md)
