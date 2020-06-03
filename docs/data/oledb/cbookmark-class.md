---
title: CBookmark クラス
ms.date: 11/04/2016
f1_keywords:
- ATL.CBookmark
- ATL::CBookmark<nSize>
- CBookmark
- ATL.CBookmark<nSize>
- ATL::CBookmark
- CBookmark<0>.CBookmark<0>
- CBookmark::CBookmark
- ATL.CBookmark.CBookmark
- CBookmark.CBookmark
- ATL::CBookmark<0>::CBookmark<0>
- ATL.CBookmark<0>.CBookmark<0>
- CBookmark<0>::CBookmark<0>
- ATL::CBookmark::CBookmark
- ATL.CBookmark<0>.GetBuffer
- ATL.CBookmark.GetBuffer
- ATL::CBookmark<0>::GetBuffer
- ATL::CBookmark::GetBuffer
- CBookmark.GetBuffer
- ATL::CBookmark<nSize>::GetBuffer
- ATL.CBookmark<nSize>.GetBuffer
- CBookmark<0>.GetBuffer
- CBookmark<nSize>::GetBuffer
- CBookmark<0>::GetBuffer
- CBookmark<nSize>.GetBuffer
- CBookmark::GetBuffer
- CBookmark::GetSize
- ATL.CBookmark<nSize>.GetSize
- CBookmark<nSize>.GetSize
- CBookmark.GetSize
- ATL::CBookmark::GetSize
- CBookmark<0>::GetSize
- ATL::CBookmark<nSize>::GetSize
- ATL.CBookmark<0>.GetSize
- ATL::CBookmark<0>::GetSize
- ATL.CBookmark.GetSize
- CBookmark<0>.GetSize
- CBookmark<nSize>::GetSize
- CBookmark<0>::SetBookmark
- ATL.CBookmark<0>.SetBookmark
- CBookmark<0>.SetBookmark
- SetBookmark
- ATL::CBookmark::SetBookmark
- ATL::CBookmark<0>::SetBookmark
- CBookmark.SetBookmark
- ATL.CBookmark.SetBookmark
- CBookmark::SetBookmark
- CBookmark<0>::operator=
- CBookmark<0>.operator=
- ATL.CBookmark.operator=
- CBookmark::operator=
- ATL.CBookmark<0>.operator=
- ATL::CBookmark<0>::operator=
- CBookmark.operator=
- ATL::CBookmark::operator=
helpviewer_keywords:
- CBookmark class
- CBookmark class, constructor
- GetBuffer method
- GetSize method
- SetBookmark method
- = operator, with OLE DB templates
- operator =, bookmarks
- operator=, bookmarks
ms.assetid: bc942f95-6f93-41d9-bb6e-bcdae4ae0b7a
ms.openlocfilehash: d3d82ea09b7ed2c1cbaf325906b4f9b480e1eb4e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359330"
---
# <a name="cbookmark-class"></a>CBookmark クラス

バッファー内のブックマーク値を保持します。

## <a name="syntax"></a>構文

```cpp
template < DBLENGTH nSize = 0 >
class CBookmark : public CBookmarkBase

template <>
class CBookmark< 0 > : public CBookmarkBase
```

### <a name="parameters"></a>パラメーター

*Nsize*<br/>
ブックマーク バッファーのサイズ (バイト単位)。 *nSize*が 0 の場合、ブックマーク バッファーは実行時に動的に作成されます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[ブックマーク](#cbookmark)|コンストラクタ|
|[GetBuffer](#getbuffer)|バッファーへのポインターを取得します。|
|[GetSize](#getsize)|バッファーのサイズをバイト単位で取得します。|
|[Setbookmark](#setbookmark)|ブックマークの値を設定します。|

### <a name="operators"></a>オペレーター

|||
|-|-|
|[演算子 =](#operator)|ある`CBookmark`クラスを別のクラスに割り当てます。|

## <a name="remarks"></a>解説

`CBookmark<0>`は のテンプレートの特殊`CBookmark`化です。バッファは実行時に動的に作成されます。

## <a name="cbookmarkcbookmark"></a><a name="cbookmark"></a>ブックマーク::C ブックマーク

コンストラクターです。

### <a name="syntax"></a>構文

```cpp
CBookmark();
CBookmark(DBLENGTH nSize);
```

#### <a name="parameters"></a>パラメーター

*Nsize*<br/>
[in]ブックマーク バッファーのサイズ (バイト単位)。

### <a name="remarks"></a>解説

最初の関数は、バッファーを NULL に、バッファー サイズを 0 に設定します。 2 番目の関数は、バッファー サイズを*nSize*に設定し、バッファーを*nSize*バイトのバイト配列に設定します。

> [!NOTE]
> この関数は`CBookmark<0>`、 でのみ使用できます。

## <a name="cbookmarkgetbuffer"></a><a name="getbuffer"></a>をクリックします。

ブックマーク バッファーへのポインターを取得します。

### <a name="syntax"></a>構文

```cpp
virtual BYTE* GetBuffer() const throw();
```

### <a name="return-value"></a>戻り値

ブックマーク バッファーへのポインター。

## <a name="cbookmarkgetsize"></a><a name="getsize"></a>次の値を設定します。

ブックマーク バッファーのサイズを取得します。

### <a name="syntax"></a>構文

```cpp
virtual DBLENGTH GetSize() const throw();
```

### <a name="return-value"></a>戻り値

バッファーのサイズ (バイト単位)。

## <a name="cbookmarksetbookmark"></a><a name="setbookmark"></a>ブックマーク:設定ブックマーク

*pBuffer*によって参照されるブックマーク値を`CBookmark`バッファーにコピーし、バッファー サイズを*nSize*に設定します。

### <a name="syntax"></a>構文

```cpp
HRESULT SetBookmark(DBLENGTH nSize, BYTE* pBuffer) throw();
```

#### <a name="parameters"></a>パラメーター

*Nsize*<br/>
[in]ブックマーク バッファーのサイズ。

*pBuffer*<br/>
[in]ブックマーク値を含むバイト配列へのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT。

### <a name="remarks"></a>解説

この関数は`CBookmark<0>`、 でのみ使用できます。

## <a name="cbookmarkoperator-"></a><a name="operator"></a>Cブックマーク::演算子 =

オブジェクトを別`CBookmark`のオブジェクトに割り当てます。

### <a name="syntax"></a>構文

```cpp
CBookmark& operator =(const CBookmark& bookmark) throw();
```

### <a name="remarks"></a>解説

この演算子は`CBookmark<0>`でだけ必要です。

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
