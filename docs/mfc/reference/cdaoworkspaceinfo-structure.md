---
title: CDaoWorkspaceInfo 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoWorkspaceInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoWorkspaceInfo structure [MFC]
- DAO (Data Access Objects), Workspaces collection
ms.assetid: a1f4b25e-f9c6-4196-b075-d1df99c54124
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f46bfec2d74b0d1fd292b3c9852ba8ea568329a2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46441760"
---
# <a name="cdaoworkspaceinfo-structure"></a>CDaoWorkspaceInfo 構造体

`CDaoWorkspaceInfo`構造体には、データ アクセス オブジェクト (DAO) のデータベース アクセスに対して定義されているワークスペースに関する情報が含まれています。

## <a name="syntax"></a>構文

```
struct CDaoWorkspaceInfo
{
    CString m_strName;           // Primary
    CString m_strUserName;       // Secondary
    BOOL m_bIsolateODBCTrans;    // All
};
```

#### <a name="parameters"></a>パラメーター

*m_strName*<br/>
Workspace オブジェクトの一意名します。 このプロパティの値を直接取得するには、クエリ定義オブジェクトを呼び出す[GetName](../../mfc/reference/cdaoquerydef-class.md#getname)メンバー関数。 詳細については、「Name プロパティ」DAO ヘルプのトピックを参照してください。

*m_strUserName*<br/>
Workspace オブジェクトの所有者を表す値。 関連情報については、「UserName プロパティ」DAO ヘルプのトピックを参照してください。

*m_bIsolateODBCTrans*<br/>
同じ ODBC データベースが関係する複数のトランザクションが分離されたかどうかを示す値。 詳細については、次を参照してください。 [CDaoWorkspace::SetIsolateODBCTrans](../../mfc/reference/cdaoworkspace-class.md#setisolateodbctrans)します。 関連情報については、「IsolateODBCTrans プロパティ」DAO ヘルプのトピックを参照してください。

## <a name="remarks"></a>Remarks

クラスのオブジェクトであるワークスペース[CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)します。 プライマリ、セカンダリ、および上記のすべてへの参照情報がによって返される方法を示すため、 [GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo)クラスのメンバー関数`CDaoWorkspace`します。

によって取得される情報、 [CDaoWorkspace::GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo)にメンバー関数が格納されている、`CDaoWorkspaceInfo`構造体。 `CDaoWorkspaceInfo` 定義、`Dump`デバッグでのメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoWorkspaceInfo`オブジェクト。

## <a name="requirements"></a>要件

**ヘッダー:** afxdao.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoWorkspace クラス](../../mfc/reference/cdaoworkspace-class.md)
