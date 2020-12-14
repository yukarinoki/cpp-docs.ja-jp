---
description: '詳細については、次を参照してください: CDaoWorkspaceInfo 構造体'
title: CDaoWorkspaceInfo 構造体
ms.date: 11/04/2016
f1_keywords:
- CDaoWorkspaceInfo
helpviewer_keywords:
- CDaoWorkspaceInfo structure [MFC]
- DAO (Data Access Objects), Workspaces collection
ms.assetid: a1f4b25e-f9c6-4196-b075-d1df99c54124
ms.openlocfilehash: b89e8787c2103244535e9458650f1f104478b748
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222204"
---
# <a name="cdaoworkspaceinfo-structure"></a>CDaoWorkspaceInfo 構造体

構造体には、 `CDaoWorkspaceInfo` データアクセスオブジェクト (DAO) データベースへのアクセスに対して定義されたワークスペースに関する情報が含まれます。

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
ワークスペースオブジェクトの名前を一意にします。 このプロパティの値を直接取得するには、querydef オブジェクトの [GetName](../../mfc/reference/cdaoquerydef-class.md#getname) メンバー関数を呼び出します。 詳細については、DAO ヘルプの「Name プロパティ」を参照してください。

*m_strUserName*<br/>
ワークスペースオブジェクトの所有者を表す値です。 関連情報については、DAO ヘルプの「UserName プロパティ」を参照してください。

*m_bIsolateODBCTrans*<br/>
同じ ODBC データベースを含む複数のトランザクションが分離されているかどうかを示す値です。 詳細については、「 [CDaoWorkspace:: Seti](../../mfc/reference/cdaoworkspace-class.md#setisolateodbctrans)」を参照してください。 関連情報については、DAO ヘルプの「IsolateODBCTrans プロパティ」を参照してください。

## <a name="remarks"></a>解説

ワークスペースは、 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)クラスのオブジェクトです。 上記の Primary、Secondary、および All への参照は、クラスの [GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) メンバー関数によって情報がどのように返されるかを示して `CDaoWorkspace` います。

[CDaoWorkspace:: GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo)メンバー関数によって取得された情報は、構造体に格納され `CDaoWorkspaceInfo` ます。 `CDaoWorkspaceInfo` は、 `Dump` デバッグビルドでメンバー関数も定義します。 を使用すると、 `Dump` オブジェクトの内容をダンプでき `CDaoWorkspaceInfo` ます。

## <a name="requirements"></a>要件

**ヘッダー:** afxdao

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック、およびメッセージマップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoWorkspace クラス](../../mfc/reference/cdaoworkspace-class.md)
