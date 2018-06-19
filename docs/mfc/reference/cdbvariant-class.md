---
title: CDBVariant クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDBVariant
- AFXDB/CDBVariant
- AFXDB/CDBVariant::CDBVariant
- AFXDB/CDBVariant::Clear
- AFXDB/CDBVariant::m_dwType
- AFXDB/CDBVariant::m_boolVal
- AFXDB/CDBVariant::m_chVal
- AFXDB/CDBVariant::m_dblVal
- AFXDB/CDBVariant::m_fltVal
- AFXDB/CDBVariant::m_iVal
- AFXDB/CDBVariant::m_lVal
- AFXDB/CDBVariant::m_pbinary
- AFXDB/CDBVariant::m_pdate
- AFXDB/CDBVariant::m_pstring
- AFXDB/CDBVariant::m_pstringA
- AFXDB/CDBVariant::m_pstringW
dev_langs:
- C++
helpviewer_keywords:
- CDBVariant [MFC], CDBVariant
- CDBVariant [MFC], Clear
- CDBVariant [MFC], m_dwType
- CDBVariant [MFC], m_boolVal
- CDBVariant [MFC], m_chVal
- CDBVariant [MFC], m_dblVal
- CDBVariant [MFC], m_fltVal
- CDBVariant [MFC], m_iVal
- CDBVariant [MFC], m_lVal
- CDBVariant [MFC], m_pbinary
- CDBVariant [MFC], m_pdate
- CDBVariant [MFC], m_pstring
- CDBVariant [MFC], m_pstringA
- CDBVariant [MFC], m_pstringW
ms.assetid: de23609c-c560-4b24-bd6b-9d8903fd5b49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27970a7d3854dca398943bfe13c67f6a4e1f92f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369084"
---
# <a name="cdbvariant-class"></a>CDBVariant クラス
MFC ODBC クラスのバリアント型を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDBVariant  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDBVariant::CDBVariant](#cdbvariant)|`CDBVariant` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDBVariant::Clear](#clear)|消去、`CDBVariant`オブジェクト。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDBVariant::m_dwType](#m_dwtype)|現在格納されている値のデータ型が含まれています。 「`DWORD`」と入力します。|  
  
### <a name="public-union-members"></a>共用体のパブリック メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDBVariant::m_boolVal](#m_boolval)|型の値を含む**BOOL**です。|  
|[CDBVariant::m_chVal](#m_chval)|型の値を含む`unsigned char`です。|  
|[CDBVariant::m_dblVal](#m_dblval)|型の値を含む**二重**です。|  
|[CDBVariant::m_fltVal](#m_fltval)|型の値を含む**float**です。|  
|[CDBVariant::m_iVal](#m_ival)|型の値を含む**短い**です。|  
|[CDBVariant::m_lVal](#m_lval)|型の値を含む**長い**です。|  
|[CDBVariant::m_pbinary](#m_pbinary)|型のオブジェクトへのポインターを含む`CLongBinary`です。|  
|[CDBVariant::m_pdate](#m_pdate)|型のオブジェクトへのポインターを含む**TIMESTAMP_STRUCT**です。|  
|[CDBVariant::m_pstring](#m_pstring)|型のオブジェクトへのポインターを含む`CString`です。|  
|[CDBVariant::m_pstringA](#m_pstringa)|ASCII へのポインターを格納[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクト。|  
|[CDBVariant::m_pstringW](#m_pstringw)|幅広いへのポインターを格納[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 `CDBVariant` 基本クラスはありません。  
  
 `CDBVariant` ような[COleVariant](../../mfc/reference/colevariant-class.md)。 ただし、 `CDBVariant` OLE を使用しません。 `CDBVariant` 値のデータ型について心配する値を格納できます。 `CDBVariant` 共用体に格納されている現在の値のデータ型を追跡します。  
  
 クラス[CRecordset](../../mfc/reference/crecordset-class.md)利用`CDBVariant`3 つのメンバー関数内のオブジェクト: `GetFieldValue`、 `GetBookmark`、および`SetBookmark`です。 たとえば、`GetFieldValue`列のデータを動的に取得することができます。 列のデータ型が、実行時に認識されていない可能性がありますので`GetFieldValue`を使用して、`CDBVariant`列のデータを格納するオブジェクト。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CDBVariant`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  
  
##  <a name="cdbvariant"></a>  CDBVariant::CDBVariant  
 Null 値を作成`CDBVariant`オブジェクト。  
  
```  
CDBVariant();
```  
  
### <a name="remarks"></a>コメント  
 セット、 [m_dwType](#m_dwtype)データ メンバーを**DBVT_NULL**です。  
  
##  <a name="clear"></a>  CDBVariant::Clear  
 クリアするには、このメンバー関数を呼び出す、`CDBVariant`オブジェクト。  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>コメント  
 場合の値、 [m_dwType](#m_dwtype)データ メンバーは**DBVT_DATE**、 **DBVT_STRING**、または**DBVT_BINARY**、 **をオフに**共用体ポインター メンバーに関連付けられているメモリを解放します。 **クリア**設定`m_dwType`に**DBVT_NULL**です。  
  
 `CDBVariant`デストラクター呼び出し**クリア**です。  
  
##  <a name="m_boolval"></a>  CDBVariant::m_boolVal  
 型の値が格納**BOOL**です。  
  
### <a name="remarks"></a>コメント  
 **M_boolVal**共用体データ メンバーが所属します。 アクセスする前に**m_boolVal**、最初の値を確認[CDBVariant::m_dwType](#m_dwtype)です。 場合`m_dwType`に設定されている**DBVT_BOOL**、し**m_boolVal**有効な値が含まれます。 それ以外の場合にアクセスする**m_boolVal**信頼性のない結果が生成されます。  
  
##  <a name="m_chval"></a>  CDBVariant::m_chVal  
 型の値が格納`unsigned char`です。  
  
### <a name="remarks"></a>コメント  
 **M_chVal**共用体データ メンバーが所属します。 アクセスする前に**m_chVal**、最初の値を確認[CDBVariant::m_dwType](#m_dwtype)です。 場合`m_dwType`に設定されている**DBVT_UCHAR**、し**m_chVal**有効な値が含まれています。 それ以外の場合にアクセスする**m_chVal**信頼性のない結果が生成されます。  
  
##  <a name="m_dblval"></a>  CDBVariant::m_dblVal  
 型の値が格納**二重**です。  
  
### <a name="remarks"></a>コメント  
 **M_dblVal**共用体データ メンバーが所属します。 アクセスする前に**m_dblVal**、最初の値を確認[CDBVariant::m_dwType](#m_dwtype)です。 場合`m_dwType`に設定されている**DBVT_DOUBLE**、し**m_dblVal**有効な値が含まれています。 それ以外の場合にアクセスする**m_dblVal**信頼性のない結果が生成されます。  
  
##  <a name="m_dwtype"></a>  CDBVariant::m_dwType  
 このデータ メンバーに現在格納されている値のデータ型が含まれています、`CDBVariant`オブジェクトの共用体データ メンバーです。  
  
### <a name="remarks"></a>コメント  
 この共用体にアクセスする前に、の値を確認する必要があります`m_dwType`共用体データ メンバーへのアクセスを決定するためにします。 次の表に、可能な値`m_dwType`と、対応する共用体データ メンバーです。  
  
|m_dwType|共用体データ メンバー|  
|---------------|-----------------------|  
|**DBVT_NULL**|共用体メンバーのアクセスに対して有効ではありません。|  
|**DBVT_BOOL**|[m_boolVal](#m_boolval)|  
|**DBVT_UCHAR**|[m_chVal](#m_chval)|  
|**DBVT_SHORT**|[m_iVal](#m_ival)|  
|**DBVT_LONG**|[m_lVal](#m_lval)|  
|**DBVT_SINGLE**|[m_fltVal](#m_fltval)|  
|**DBVT_DOUBLE**|[m_dblVal](#m_dblval)|  
|**DBVT_DATE**|[m_pdate](#m_pdate)|  
|**DBVT_STRING**|[m_pstring](#m_pstring)|  
|**DBVT_BINARY**|[m_pbinary](#m_pbinary)|  
|**DBVT_ASTRING**|[m_pstringA](#m_pstringa)|  
|**DBVT_WSTRING**|[m_pstringW](#m_pstringw)|  
  
##  <a name="m_fltval"></a>  CDBVariant::m_fltVal  
 型の値が格納**float**です。  
  
### <a name="remarks"></a>コメント  
 **M_fltVal**共用体データ メンバーが所属します。 アクセスする前に**m_fltVal**、最初の値を確認[CDBVariant::m_dwType](#m_dwtype)です。 場合`m_dwType`に設定されている**DBVT_SINGLE**、し**m_fltVal**有効な値が含まれています。 それ以外の場合にアクセスする**m_fltVal**信頼性のない結果が生成されます。  
  
##  <a name="m_ival"></a>  CDBVariant::m_iVal  
 型の値が格納**短い**です。  
  
### <a name="remarks"></a>コメント  
 **M_iVal**共用体データ メンバーが所属します。 アクセスする前に**m_iVal**、最初の値を確認[CDBVariant::m_dwType](#m_dwtype)です。 場合`m_dwType`に設定されている**DBVT_SHORT**、し**m_iVal**有効な値が含まれています。 それ以外の場合にアクセスする**m_iVal**信頼性のない結果が生成されます。  
  
##  <a name="m_lval"></a>  CDBVariant::m_lVal  
 型の値が格納**長い**です。  
  
### <a name="remarks"></a>コメント  
 **M_lVal**共用体データ メンバーが所属します。 アクセスする前に**m_lVal**、最初の値を確認[CDBVariant::m_dwType](#m_dwtype)です。 場合`m_dwType`に設定されている**DBVT_LONG**、し**m_lVal**有効な値が含まれています。 それ以外の場合にアクセスする**m_lVal**信頼性のない結果が生成されます。  
  
##  <a name="m_pbinary"></a>  CDBVariant::m_pbinary  
 型のオブジェクトへのポインターを格納[CLongBinary](../../mfc/reference/clongbinary-class.md)です。  
  
### <a name="remarks"></a>コメント  
 **M_pbinary**共用体データ メンバーが所属します。 アクセスする前に**m_pbinary**、最初の値を確認[CDBVariant::m_dwType](#m_dwtype)です。 場合`m_dwType`に設定されている**DBVT_BINARY**、し**m_pbinary**の有効なポインターが含まれています。 それ以外の場合にアクセスする**m_pbinary**信頼性のない結果が生成されます。  
  
##  <a name="m_pdate"></a>  CDBVariant::m_pdate  
 型のオブジェクトへのポインターを格納**TIMESTAMP_STRUCT**です。  
  
### <a name="remarks"></a>コメント  
 **M_pdate**共用体データ メンバーが所属します。 アクセスする前に**m_pdate**、最初の値を確認[CDBVariant::m_dwType](#m_dwtype)です。 場合`m_dwType`に設定されている**DBVT_DATE**、し**m_pdate**の有効なポインターが含まれています。 それ以外の場合にアクセスする**m_pdate**信頼性のない結果が生成されます。  
  
 詳細については、 **TIMESTAMP_STRUCT**データ型を参照してください[C データ型](https://msdn.microsoft.com/library/ms714556.aspx)の付録 D に、 *ODBC プログラマ リファレンス*Windows SDK に含まれています。  
  
##  <a name="m_pstring"></a>  CDBVariant::m_pstring  
 型のオブジェクトへのポインターを格納[CString](../../atl-mfc-shared/reference/cstringt-class.md)です。  
  
### <a name="remarks"></a>コメント  
 **M_pstring**共用体データ メンバーが所属します。 アクセスする前に**m_pstring**、最初の値を確認[CDBVariant::m_dwType](#m_dwtype)です。 場合`m_dwType`に設定されている**DBVT_STRING**、し**m_pstring**の有効なポインターが含まれています。 それ以外の場合にアクセスする**m_pstring**信頼性のない結果が生成されます。  
  
##  <a name="m_pstringa"></a>  CDBVariant::m_pstringA  
 ASCII へのポインターを格納[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクト。  
  
### <a name="remarks"></a>コメント  
 **M_pstringA**共用体データ メンバーが所属します。 アクセスする前に**m_pstringA**、最初の値を確認[CDBVariant::m_dwType](#m_dwtype)です。 場合`m_dwType`に設定されている**DBVT_ASTRING**、し**m_pstringA**の有効なポインターが含まれています。 それ以外の場合にアクセスする**m_pstringA**信頼性のない結果が生成されます。  
  
##  <a name="m_pstringw"></a>  CDBVariant::m_pstringW  
 幅広いへのポインターを格納[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクト。  
  
### <a name="remarks"></a>コメント  
 **M_pstringW**共用体データ メンバーが所属します。 アクセスする前に**m_pstringW**、最初の値を確認[CDBVariant::m_dwType](#m_dwtype)です。 場合`m_dwType`に設定されている**DBVT_WSTRING**、し**m_pstringW**の有効なポインターが含まれています。 それ以外の場合にアクセスする**m_pstringW**信頼性のない結果が生成されます。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRecordset クラス](../../mfc/reference/crecordset-class.md)
