---
title: クラスを呼び出す
ms.date: 11/04/2016
f1_keywords:
- CAtlException
- ATLEXCEPT/ATL::CAtlException
- ATLEXCEPT/ATL::CAtlException::CAtlException
- ATLEXCEPT/ATL::CAtlException::m_hr
helpviewer_keywords:
- CAtlException class
ms.assetid: 3fd7b041-f70d-4292-b947-0d70781d95a8
ms.openlocfilehash: 6da56e4d6c443520eb6f857624a5923e71a1e580
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318995"
---
# <a name="catlexception-class"></a>クラスを呼び出す

このクラスは ATL 例外を定義します。

## <a name="syntax"></a>構文

```
class CAtlException
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[カトル例外::カトル例外](#catlexception)|コンストラクターです。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[呼び出し例外::演算子 HRESULT](#operator_hresult)|現在のオブジェクトを HRESULT 値にキャストします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[カトル例外::m_hr](#m_hr)|オブジェクトによって作成され、エラー条件を格納するために使用される HRESULT 型の変数。|

## <a name="remarks"></a>解説

オブジェクト`CAtlException`は、ATL 操作に関連する例外条件を表します。 クラス`CAtlException`には、例外の理由を示す状態コードを格納するパブリック データ メンバーと、例外を HRESULT であるかのように扱うためのキャスト演算子が含まれています。

一般に、オブジェクトを`AtlThrow`直接作成するのではなく、`CAtlException`呼び出します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlexcept.h

## <a name="catlexceptioncatlexception"></a><a name="catlexception"></a>カトル例外::カトル例外

コンストラクターです。

```
CAtlException(HRESULT hr) throw();
CAtlException() throw();
```

### <a name="parameters"></a>パラメーター

*人事*<br/>
HRESULT エラー コード。

## <a name="catlexceptionoperator-hresult"></a><a name="operator_hresult"></a>呼び出し例外::演算子 HRESULT

現在のオブジェクトを HRESULT 値にキャストします。

```
operator HRESULT() const throw ();
```

## <a name="catlexceptionm_hr"></a><a name="m_hr"></a>カトル例外::m_hr

HRESULT データ メンバー。

```
HRESULT m_hr;
```

### <a name="remarks"></a>解説

エラー条件を格納するデータ メンバー。 HRESULT 値は、コンストラクターによって設定[されます](#catlexception)。

## <a name="see-also"></a>関連項目

[AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
