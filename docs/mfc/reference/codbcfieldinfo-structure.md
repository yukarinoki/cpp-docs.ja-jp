---
title: CODBCFieldInfo 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CODBCFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- ODBC [MFC], data source information
- CODBCFieldInfo structure [MFC]
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1723e93320129fae232bb850caa123d1638a37b
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37853083"
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
 *m_strName*  
 フィールドの名前。  
  
 *m_nSQLType*  
 フィールドの SQL データ型。 これには、ODBC SQL データ型をまたはドライバーに固有の SQL データ型を指定できます。 有効な ODBC SQL データ型の一覧は、Windows SDK の「SQL データ型」を参照してください。 ドライバー固有の SQL データ型については、ドライバーのドキュメントを参照してください。  
  
 *m_nPrecision*  
 フィールドの最大有効桁数。 詳細については、Windows SDK の「有効桁数、スケール、長さ、および表示サイズ」を参照してください。  
  
 *m_nScale*  
 フィールドの小数点以下桁数。 詳細については、Windows SDK の「有効桁数、スケール、長さ、および表示サイズ」を参照してください。  
  
 *m_nNullability*  
 かどうか、フィールドは、Null 値を受け入れます。 これは 2 つの値のいずれかを指定できます: SQL_NULLABLE フィールドは Null 値を受け入れるか SQL_NO_NULLS フィールドを受け入れない場合は Null 値。  
  
## <a name="remarks"></a>Remarks  
 この情報を取得する[に](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdb.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [に](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)   
 [CRecordset::GetFieldValue](../../mfc/reference/crecordset-class.md#getfieldvalue)


