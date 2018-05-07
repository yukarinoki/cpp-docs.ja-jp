---
title: CDaoWorkspaceInfo 構造体 |Microsoft ドキュメント
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
ms.openlocfilehash: dd6979124916e8a9cc1dc723008491bababc0322
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cdaoworkspaceinfo-structure"></a>CDaoWorkspaceInfo 構造体
`CDaoWorkspaceInfo`構造体には、データ アクセス オブジェクト (DAO) データベースへのアクセスに対して定義されているワークスペースについての情報が含まれています。  
  
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
 `m_strName`  
 ワークスペースのオブジェクトの一意名です。 このプロパティの値を直接取得するを呼び出すクエリ定義オブジェクトの[GetName](../../mfc/reference/cdaoquerydef-class.md#getname)メンバー関数。 詳細については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
 *m_strUserName*  
 ワークスペースのオブジェクトの所有者を表す値。 関連情報については、DAO ヘルプの「ユーザー名プロパティ」を参照してください。  
  
 *m_bIsolateODBCTrans*  
 同じ ODBC データベースを含む複数のトランザクションが分離されたかどうかを示す値。 詳細については、次を参照してください。 [CDaoWorkspace::SetIsolateODBCTrans](../../mfc/reference/cdaoworkspace-class.md#setisolateodbctrans)です。 関連情報については、DAO ヘルプの「IsolateODBCTrans プロパティ」を参照してください。  
  
## <a name="remarks"></a>コメント  
 クラスのオブジェクトであるワークスペース[CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)です。 プライマリ、セカンダリ、および上記のすべての参照は、情報がによって返される方法を示します、 [GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo)クラスのメンバー関数`CDaoWorkspace`です。  
  
 によって取得される情報、 [CDaoWorkspace::GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo)メンバー関数は、`CDaoWorkspaceInfo`構造体。 `CDaoWorkspaceInfo` 定義、`Dump`デバッグでメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoWorkspaceInfo`オブジェクト。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoWorkspace クラス](../../mfc/reference/cdaoworkspace-class.md)
