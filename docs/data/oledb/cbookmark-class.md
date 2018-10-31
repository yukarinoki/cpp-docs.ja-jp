---
title: CBookmark クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
- CBookmark
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: aef24c5c55bc3a3250c483536d0a63f967608b20
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50064336"
---
# <a name="cbookmark-class"></a>CBookmark クラス

バッファーには、ブックマークの値を保持します。

## <a name="syntax"></a>構文

```cpp
template < DBLENGTH nSize = 0 >
class CBookmark : public CBookmarkBase

template <>
class CBookmark< 0 > : public CBookmarkBase
```

### <a name="parameters"></a>パラメーター

*nSize*<br/>
ブックマーク バッファーのバイト単位のサイズ。 ときに*nSize* 0 の場合は、実行時に、ブックマークのバッファーを動的に作成されます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[CBookmark](#cbookmark)|コンス トラクター|
|[GetBuffer](#getbuffer)|バッファーへのポインターを取得します。|
|[GetSize](#getsize)|バッファーのバイト単位のサイズを取得します。|
|[SetBookmark](#setbookmark)|ブックマークの値を設定します。|

### <a name="operators"></a>演算子

|||
|-|-|
|[演算子 =](#operator)|1 つ割り当てます`CBookmark`を別のクラス。|

## <a name="remarks"></a>Remarks

`CBookmark<0>` テンプレート特殊化した`CBookmark`; 実行時に、バッファーが動的に作成します。

## <a name="cbookmark"></a> Cbookmark::cbookmark

コンストラクターです。

### <a name="syntax"></a>構文

```cpp
CBookmark();
 
CBookmark(DBLENGTH nSize);
```

#### <a name="parameters"></a>パラメーター

*nSize*<br/>
[in]ブックマーク バッファーのバイト単位のサイズ。

### <a name="remarks"></a>Remarks

最初の関数では、バッファーを NULL とバッファー サイズを 0 に設定します。 2 番目の関数では、バッファー サイズを設定*nSize*、およびバッファーのバイト配列を*nSize*バイト。

> [!NOTE]
>  この関数はのみ`CBookmark<0>`します。

## <a name="getbuffer"></a> Cbookmark::getbuffer

ブックマーク バッファーへのポインターを取得します。

### <a name="syntax"></a>構文

```cpp
virtual BYTE* GetBuffer() const throw();
```

### <a name="return-value"></a>戻り値

ブックマーク バッファーへのポインター。

## <a name="getsize"></a> Cbookmark::getsize

ブックマークのバッファーのサイズを取得します。

### <a name="syntax"></a>構文

```cpp
virtual DBLENGTH GetSize() const throw();
```

### <a name="return-value"></a>戻り値

バッファーのサイズ (バイト単位)。

## <a name="setbookmark"></a> Cbookmark::setbookmark

によって参照されるブックマークの値をコピー *pBuffer*を`CBookmark`バッファーおよびバッファー サイズを設定します*nSize*します。

### <a name="syntax"></a>構文

```cpp
HRESULT SetBookmark(DBLENGTH nSize, BYTE* pBuffer) throw();
```

#### <a name="parameters"></a>パラメーター

*nSize*<br/>
[in]ブックマークのバッファーのサイズ。

*pBuffer*<br/>
[in]ブックマークの値を格納するバイト配列へのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>Remarks

この関数はのみ`CBookmark<0>`します。

## <a name="operator"></a> Cbookmark::operator =

割り当てます、`CBookmark`を別のオブジェクト。

### <a name="syntax"></a>構文

```cpp
CBookmark& operator =(const CBookmark& bookmark) throw();
```

### <a name="remarks"></a>Remarks

この演算子はのみに必要な`CBookmark<0>`します。

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)