---
description: '詳細情報: CODBCFieldInfo 構造体'
title: CODBCFieldInfo 構造体
ms.date: 11/04/2016
f1_keywords:
- CODBCFieldInfo
helpviewer_keywords:
- ODBC [MFC], data source information
- CODBCFieldInfo structure [MFC]
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
ms.openlocfilehash: 7cd7072719bec46cfbfaeb02c5c86d714c4de13c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331415"
---
# <a name="codbcfieldinfo-structure"></a>CODBCFieldInfo 構造体

構造体には、 `CODBCFieldInfo` ODBC データソースのフィールドに関する情報が含まれています。

## <a name="syntax"></a>構文

```
struct CODBCFieldInfo
{
    CString m_strName;
    SWORD m_nSQLType;
    UDWORD m_nPrecision;
    SWORD m_nScale;
    SWORD m_nNullability;
};
```

#### <a name="parameters"></a>パラメーター

*m_strName*<br/>
フィールドの名前。

*m_nSQLType*<br/>
フィールドの SQL データ型です。 ODBC SQL データ型またはドライバー固有の SQL データ型を指定できます。 有効な ODBC SQL データ型の一覧については、Windows SDK の「SQL データ型」を参照してください。 ドライバー固有の SQL データ型の詳細については、ドライバーのドキュメントを参照してください。

*m_nPrecision*<br/>
フィールドの最大有効桁数。 詳細については、Windows SDK の「有効桁数、小数点以下桁数、長さ、および表示サイズ」を参照してください。

*m_nScale*<br/>
フィールドの小数点以下桁数です。 詳細については、Windows SDK の「有効桁数、小数点以下桁数、長さ、および表示サイズ」を参照してください。

*m_nNullability*<br/>
フィールドが Null 値を受け入れるかどうかを指定します。 この値には、フィールドが Null 値を許容する場合は SQL_NULLABLE、Null 値を許容しない場合は SQL_NO_NULLS のいずれかを指定できます。

## <a name="remarks"></a>解説

この情報を取得するには、 [CRecordset:: GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)を呼び出します。

## <a name="requirements"></a>要件

**ヘッダー:** afxdb.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック、およびメッセージマップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CRecordset:: GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)<br/>
[CRecordset:: GetFieldValue](../../mfc/reference/crecordset-class.md#getfieldvalue)
