---
title: CODBCFieldInfo 構造体
ms.date: 11/04/2016
f1_keywords:
- CODBCFieldInfo
helpviewer_keywords:
- ODBC [MFC], data source information
- CODBCFieldInfo structure [MFC]
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
ms.openlocfilehash: 5ad7d8f710c763b25771e3d1fa8839b5b64802ad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50655274"
---
# <a name="codbcfieldinfo-structure"></a>CODBCFieldInfo 構造体

`CODBCFieldInfo`構造体には、ODBC データ ソースのフィールドについての情報が含まれています。

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
フィールドの SQL データ型。 これには、ODBC SQL データ型をまたはドライバーに固有の SQL データ型を指定できます。 有効な ODBC SQL データ型の一覧は、Windows SDK の「SQL データ型」を参照してください。 ドライバー固有の SQL データ型については、ドライバーのドキュメントを参照してください。

*m_nPrecision*<br/>
フィールドの最大有効桁数。 詳細については、Windows SDK の「有効桁数、スケール、長さ、および表示サイズ」を参照してください。

*m_nScale*<br/>
フィールドの小数点以下桁数。 詳細については、Windows SDK の「有効桁数、スケール、長さ、および表示サイズ」を参照してください。

*m_nNullability*<br/>
かどうか、フィールドは、Null 値を受け入れます。 これは 2 つの値のいずれかを指定できます: SQL_NULLABLE フィールドは Null 値を受け入れるか SQL_NO_NULLS フィールドを受け入れない場合は Null 値。

## <a name="remarks"></a>Remarks

この情報を取得する[に](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)します。

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[に](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)<br/>
[CRecordset::GetFieldValue](../../mfc/reference/crecordset-class.md#getfieldvalue)

