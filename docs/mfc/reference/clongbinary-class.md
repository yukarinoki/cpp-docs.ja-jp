---
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
ms.openlocfilehash: 1ce1daba90f3a1dad4b9627082d63f1b3405eab4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370133"
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
|[コロングバイナリ::コロングバイナリ](#clongbinary)|`CLongBinary` オブジェクトを構築します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[コロングバイナリ::m_dwDataLength](#m_dwdatalength)|ハンドルが に格納されているデータ オブジェクトの実際のサイズ (`m_hData`バイト単位) を格納します。|
|[長いバイナリ::m_hData](#m_hdata)|実際のイメージ オブジェクトへの Windows HGLOBAL ハンドルを格納します。|

## <a name="remarks"></a>解説

たとえば、SQL テーブルのレコード フィールドには、ピクチャを表すビットマップが含まれている場合があります。 オブジェクト`CLongBinary`は、このようなオブジェクトを格納し、そのサイズを追跡します。

> [!NOTE]
> 一般的に[、cByteArray](../../mfc/reference/cbytearray-class.md)を[DFX_Binary](record-field-exchange-functions.md#dfx_binary)関数と組み合わせて使用することをお勧めします。 それでも引き続`CLongBinary`き使用できますが、16 ビット`CByteArray``CByteArray`で発生するサイズ制限がなくなったため、一般に Win32 ではより多くの機能が提供されます。 このアドバイスは、データ アクセス オブジェクト (DAO) とオープン データベース接続 (ODBC) を使用したプログラミングに適用されます。

オブジェクトを`CLongBinary`使用するには、レコードセット クラスで型`CLongBinary`のフィールド データ メンバーを宣言します。 このメンバは、レコードセット クラスの埋め込みメンバであり、レコードセットの作成時に作成されます。 オブジェクトが`CLongBinary`構築されると、レコード フィールド エクスチェンジ (RFX) メカニズムは、データ ソースの現在のレコードのフィールドからデータ オブジェクトを読み込み、レコードが更新されたときにレコードに格納します。 RFX は、データ ソースにバイナリ ラージ オブジェクトのサイズを問い合わせ、その`CLongBinary`データ ソース`m_hData`にストレージを割り当`HGLOBAL`て (オブジェクトの`m_hData`データ メンバーを介して) し、データへのハンドルを . また、RFX はデータ メンバーにデータ オブジェクト`m_dwDataLength`の実際のサイズも格納します。 オブジェクト内のデータを使用して`m_hData`、 Windows`HGLOBAL`ハンドルに格納されているデータを操作する場合と同じ手法を使用します。

レコードセットを破棄すると、埋め`CLongBinary`込みオブジェクトも破棄され、デストラクタによってデータ`HGLOBAL`ハンドルが解放されます。

ラージ オブジェクトの詳細と`CLongBinary`の使用方法については、「[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md) 」および「[レコードセット: 大きなデータ項目の操作 (ODBC)」](../../data/odbc/recordset-working-with-large-data-items-odbc.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CLongBinary`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdb_.h

## <a name="clongbinaryclongbinary"></a><a name="clongbinary"></a>コロングバイナリ::コロングバイナリ

`CLongBinary` オブジェクトを構築します。

```
CLongBinary();
```

## <a name="clongbinarym_dwdatalength"></a><a name="m_dwdatalength"></a>コロングバイナリ::m_dwDataLength

の HGLOBAL ハンドルに格納されているデータの実際のサイズをバイト`m_hData`単位で格納します。

```
SQLULEN m_dwDataLength;
```

### <a name="remarks"></a>解説

このサイズは、データに割り当てられたメモリ ブロックのサイズよりも小さくなる可能性があります。 割り当てられたサイズを取得するのには、Win32 [GLobalSize](/windows/win32/api/winbase/nf-winbase-globalsize)関数を呼び出します。

## <a name="clongbinarym_hdata"></a><a name="m_hdata"></a>長いバイナリ::m_hData

実際のバイナリ ラージ オブジェクト データへの Windows HGLOBAL ハンドルを格納します。

```
HGLOBAL m_hData;
```

## <a name="see-also"></a>関連項目

[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/crecordset-class.md)
