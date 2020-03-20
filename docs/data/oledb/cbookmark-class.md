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
ms.openlocfilehash: 89c7e62e51adbe96bee870b4baa8a35784b61ac0
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79546027"
---
# <a name="cbookmark-class"></a>CBookmark クラス

ブックマークの値をバッファーに保持します。

## <a name="syntax"></a>構文

```cpp
template < DBLENGTH nSize = 0 >
class CBookmark : public CBookmarkBase

template <>
class CBookmark< 0 > : public CBookmarkBase
```

### <a name="parameters"></a>パラメーター

*nSize*<br/>
ブックマークバッファーのサイズ (バイト単位)。 *NSize*が0の場合、ブックマークバッファーは実行時に動的に作成されます。

## <a name="requirements"></a>要件

**ヘッダー:** atldbcli.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[CBookmark](#cbookmark)|コンストラクター|
|[GetBuffer](#getbuffer)|バッファーへのポインターを取得します。|
|[GetSize](#getsize)|バッファーのサイズ (バイト単位) を取得します。|
|[SetBookmark](#setbookmark)|ブックマーク値を設定します。|

### <a name="operators"></a>演算子

|||
|-|-|
|[operator =](#operator)|1つの `CBookmark` クラスを別のクラスに割り当てます。|

## <a name="remarks"></a>コメント

`CBookmark<0>` は、`CBookmark`のテンプレートに特殊化されています。そのバッファーは実行時に動的に作成されます。

## <a name="cbookmarkcbookmark"></a><a name="cbookmark"></a>CBookmark:: CBookmark

コンストラクターです。

### <a name="syntax"></a>構文

```cpp
CBookmark();
CBookmark(DBLENGTH nSize);
```

#### <a name="parameters"></a>パラメーター

*nSize*<br/>
からブックマークバッファーのサイズ (バイト単位)。

### <a name="remarks"></a>コメント

最初の関数は、バッファーを NULL に設定し、バッファーサイズを0に設定します。 2番目の関数は、バッファーサイズを*nSize*に、バッファーを*nSize*バイトのバイト配列に設定します。

> [!NOTE]
>  この関数は、`CBookmark<0>`でのみ使用できます。

## <a name="cbookmarkgetbuffer"></a><a name="getbuffer"></a>CBookmark:: GetBuffer

ブックマークバッファーへのポインターを取得します。

### <a name="syntax"></a>構文

```cpp
virtual BYTE* GetBuffer() const throw();
```

### <a name="return-value"></a>戻り値

ブックマークバッファーへのポインター。

## <a name="cbookmarkgetsize"></a><a name="getsize"></a>CBookmark:: GetSize

ブックマークバッファーのサイズを取得します。

### <a name="syntax"></a>構文

```cpp
virtual DBLENGTH GetSize() const throw();
```

### <a name="return-value"></a>戻り値

バッファーのサイズ (バイト単位)。

## <a name="cbookmarksetbookmark"></a><a name="setbookmark"></a>CBookmark:: SetBookmark

*Pbuffer*によって参照されるブックマーク値を `CBookmark` バッファーにコピーし、バッファーサイズを*nSize*に設定します。

### <a name="syntax"></a>構文

```cpp
HRESULT SetBookmark(DBLENGTH nSize, BYTE* pBuffer) throw();
```

#### <a name="parameters"></a>パラメーター

*nSize*<br/>
からブックマークバッファーのサイズ。

*pBuffer*<br/>
からブックマーク値を格納しているバイト配列へのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>コメント

この関数は、`CBookmark<0>`でのみ使用できます。

## <a name="cbookmarkoperator-"></a><a name="operator"></a>CBookmark:: operator =

`CBookmark` オブジェクトを別のオブジェクトに割り当てます。

### <a name="syntax"></a>構文

```cpp
CBookmark& operator =(const CBookmark& bookmark) throw();
```

### <a name="remarks"></a>コメント

この操作は、`CBookmark<0>`でのみ必要です。

## <a name="see-also"></a>参照

[OLE DB コンシューマー テンプレートに関するページ](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)