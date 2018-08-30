---
title: CLongBinary クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CLongBinary
- AFXDB_/CLongBinary
- AFXDB_/CLongBinary::CLongBinary
- AFXDB_/CLongBinary::m_dwDataLength
- AFXDB_/CLongBinary::m_hData
dev_langs:
- C++
helpviewer_keywords:
- CLongBinary class [MFC]
ms.assetid: f4320059-aeb4-4ee5-bc2b-25f19d898ef5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ed0603482ffccf1bcb827d67b174768cfd3e3168
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43196798"
---
# <a name="clongbinary-class"></a>CLongBinary クラス
データベース上の大きなバイナリ データ オブジェクト (BLOB または "バイナリ ラージ オブジェクト" と呼びます) を使った作業を単純にします。  
  
## <a name="syntax"></a>構文  
  
```  
class CLongBinary : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CLongBinary::CLongBinary](#clongbinary)|`CLongBinary` オブジェクトを構築します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CLongBinary::m_dwDataLength](#m_dwdatalength)|実際のサイズにハンドルが格納されているデータ オブジェクトのバイトが含まれています`m_hData`します。|  
|[CLongBinary::m_hData](#m_hdata)|実際の画像オブジェクトへの Windows HGLOBAL ハンドルが含まれています。|  
  
## <a name="remarks"></a>Remarks  
 たとえば、SQL テーブル内のレコード フィールドには、画像のビットマップが含まれます。 A`CLongBinary`オブジェクトは、このようなオブジェクトを格納およびのサイズを追跡します。  
  
> [!NOTE]
>  一般に、使用する方が優れた実装のようになりましたが[CByteArray](../../mfc/reference/cbytearray-class.md)と組み合わせて、 [DFX_Binary](record-field-exchange-functions.md#dfx_binary)関数。 使用することもできます`CLongBinary`が、一般に`CByteArray`機能が増える win32 で不要であるため、16 ビットで発生したサイズの制限`CByteArray`します。 このアドバイスは、データ アクセス オブジェクト (DAO) とオープン データベース コネクティビティ (ODBC) を使用したプログラミングに適用されます。  
  
 使用する、`CLongBinary`オブジェクト、型のフィールド データ メンバーを宣言`CLongBinary`レコード セット クラスでします。 このメンバーは、レコード セット クラスの埋め込みのメンバーにして、レコード セットが作成されるときに構築されます。 後に、`CLongBinary`オブジェクトが作成されると、レコード フィールド エクス (チェンジ RFX) メカニズムがデータ ソースの現在のレコードのフィールドからのデータ オブジェクトの読み込みし、レコードが更新されたときに、レコードに格納します。 RFX をバイナリ ラージ オブジェクトのサイズがストレージを割り当ててのデータ ソースのクエリ (を使用して、`CLongBinary`オブジェクトの`m_hData`データ メンバー)、し、格納、`HGLOBAL`内のデータへのハンドル`m_hData`します。 RFX も内のデータ オブジェクトの実際のサイズを格納、`m_dwDataLength`データ メンバー。 使用してオブジェクトにデータを扱う`m_hData`は通常、Windows に格納されているデータの操作に使用する同じ手法を使用して`HGLOBAL`を処理します。  
  
 埋め込まれたレコード セットを破棄する`CLongBinary`オブジェクトが破棄されることも、およびそのデストラクターが割り当て解除、`HGLOBAL`データ ハンドル。  
  
 ラージ オブジェクトとの使用の詳細については`CLongBinary`、記事を参照して[レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)と[レコード セット: 大規模なデータ項目 (ODBC) での作業](../../data/odbc/recordset-working-with-large-data-items-odbc.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CLongBinary`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdb_.h  
  
##  <a name="clongbinary"></a>  CLongBinary::CLongBinary  
 `CLongBinary` オブジェクトを構築します。  
  
```  
CLongBinary();
```  
  
##  <a name="m_dwdatalength"></a>  CLongBinary::m_dwDataLength  
 HGLOBAL のハンドルに格納されたデータのバイト単位の実際のサイズを格納`m_hData`します。  
  
```  
SQLULEN m_dwDataLength;  
```  
  
### <a name="remarks"></a>Remarks  
 このサイズは、データに割り当てられたメモリ ブロックのサイズよりも小さい可能性があります。 Win32 呼び出し[GLobalSize](/windows/desktop/api/winbase/nf-winbase-globalsize)割り当てサイズを取得します。  
  
##  <a name="m_hdata"></a>  CLongBinary::m_hData  
 実際のバイナリ ラージ オブジェクト データを識別する Windows HGLOBAL のハンドルを格納します。  
  
```  
HGLOBAL m_hData;  
```  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRecordset クラス](../../mfc/reference/crecordset-class.md)
