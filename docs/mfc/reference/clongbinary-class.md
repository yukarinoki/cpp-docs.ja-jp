---
description: '詳細情報: CLongBinary クラス'
title: CLongBinary クラス
ms.date: 11/04/2016
f1_keywords:
- CLongBinary
- AFXDB_/CLongBinary
- AFXDB_/CLongBinary::CLongBinary
- AFXDB_/CLongBinary::m_dwDataLength
- AFXDB_/CLongBinary::m_hData
helpviewer_keywords:
- CLongBinary class [MFC]
ms.assetid: f4320059-aeb4-4ee5-bc2b-25f19d898ef5
ms.openlocfilehash: ad6836ce6ee7e95929f69d226dcab61fc5482277
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336723"
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
|[CLongBinary:: CLongBinary](#clongbinary)|`CLongBinary` オブジェクトを構築します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CLongBinary:: m_dwDataLength](#m_dwdatalength)|ハンドルがに格納されているデータオブジェクトの実際のサイズ (バイト単位) を格納し `m_hData` ます。|
|[CLongBinary:: m_hData](#m_hdata)|実際のイメージオブジェクトを表す Windows の HGLOBAL ハンドルを格納します。|

## <a name="remarks"></a>解説

たとえば、SQL テーブルのレコードフィールドには、画像を表すビットマップが含まれている場合があります。 オブジェクトは、その `CLongBinary` ようなオブジェクトを格納し、そのサイズを追跡します。

> [!NOTE]
> 一般に、 [DFX_Binary](record-field-exchange-functions.md#dfx_binary)関数と共に[CByteArray](../../mfc/reference/cbytearray-class.md)を使用することをお勧めします。 引き続きを使用することもでき `CLongBinary` ますが、一般的に、Win32 では `CByteArray` より多くの機能が提供されます。これは、16ビットで発生したサイズの制限がなくなったためです `CByteArray` 。 このアドバイスは、データアクセスオブジェクト (DAO) と Open Database Connectivity (ODBC) を使用したプログラミングに適用されます。

オブジェクトを使用するには `CLongBinary` 、 `CLongBinary` レコードセットクラスで型のフィールドデータメンバーを宣言します。 このメンバーはレコードセットクラスの埋め込みメンバーになり、レコードセットの構築時に作成されます。 `CLongBinary`オブジェクトが構築されると、レコードフィールドエクスチェンジ (RFX) メカニズムによって、データソースの現在のレコードのフィールドからデータオブジェクトが読み込まれ、レコードが更新されるとレコードに保存されます。 RFX は、バイナリラージオブジェクトのサイズをデータソースに照会し、そのデータのストレージを ( `CLongBinary` オブジェクトのデータメンバーを介して) 割り当て、 `m_hData` `HGLOBAL` データへのハンドルをに格納し `m_hData` ます。 また、RFX では、データオブジェクトの実際のサイズもデータメンバーに格納され `m_dwDataLength` ます。 `m_hData`Windows ハンドルに格納されているデータの操作に通常使用するのと同じ手法を使用して、オブジェクト内のデータを使用して操作し `HGLOBAL` ます。

レコードセットを破棄すると、埋め込み `CLongBinary` オブジェクトも破棄され、そのデストラクターが `HGLOBAL` データハンドルを解放します。

ラージオブジェクトとの使用の詳細については `CLongBinary` 、「 [レコードセット (odbc)](../../data/odbc/recordset-odbc.md) 」および「 [レコードセット: 大規模なデータ項目の操作 (odbc)](../../data/odbc/recordset-working-with-large-data-items-odbc.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CLongBinary`

## <a name="requirements"></a>要件

**ヘッダー:** afxdb_

## <a name="clongbinaryclongbinary"></a><a name="clongbinary"></a> CLongBinary:: CLongBinary

`CLongBinary` オブジェクトを構築します。

```
CLongBinary();
```

## <a name="clongbinarym_dwdatalength"></a><a name="m_dwdatalength"></a> CLongBinary:: m_dwDataLength

の HGLOBAL ハンドルに格納されているデータの実際のサイズをバイト単位で格納し `m_hData` ます。

```
SQLULEN m_dwDataLength;
```

### <a name="remarks"></a>解説

このサイズは、データに割り当てられたメモリブロックのサイズよりも小さくなる場合があります。 割り当てられたサイズを取得するには、Win32 [Globalsize](/windows/win32/api/winbase/nf-winbase-globalsize) 関数を呼び出します。

## <a name="clongbinarym_hdata"></a><a name="m_hdata"></a> CLongBinary:: m_hData

Windows の HGLOBAL ハンドルを実際のバイナリラージオブジェクトデータに格納します。

```
HGLOBAL m_hData;
```

## <a name="see-also"></a>関連項目

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CRecordset クラス](../../mfc/reference/crecordset-class.md)
