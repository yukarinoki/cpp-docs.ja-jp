---
title: CAtlException クラス
ms.date: 11/04/2016
f1_keywords:
- CAtlException
- ATLEXCEPT/ATL::CAtlException
- ATLEXCEPT/ATL::CAtlException::CAtlException
- ATLEXCEPT/ATL::CAtlException::m_hr
helpviewer_keywords:
- CAtlException class
ms.assetid: 3fd7b041-f70d-4292-b947-0d70781d95a8
ms.openlocfilehash: f09d9b2f46233cf356f5ade8a5b90e08a213d276
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168203"
---
# <a name="catlexception-class"></a>CAtlException クラス

このクラスは、ATL 例外を定義します。

## <a name="syntax"></a>構文

```cpp
class CAtlException
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CAtlException::CAtlException](#catlexception)|コンストラクターです。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CAtlException:: operator HRESULT](#operator_hresult)|現在のオブジェクトを HRESULT 値にキャストします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CAtlException:: m_hr](#m_hr)|オブジェクトによって作成され、エラー状態を格納するために使用される HRESULT 型の変数。|

## <a name="remarks"></a>解説

オブジェクト`CAtlException`は、ATL 操作に関連する例外条件を表します。 クラス`CAtlException`には、例外の理由を示すステータスコードを格納するパブリックデータメンバーと、例外を HRESULT として扱うことができるキャスト演算子が含まれています。

一般に、オブジェクトを`AtlThrow` `CAtlException`直接作成するのではなく、を呼び出します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlexcept. h

## <a name="catlexceptioncatlexception"></a><a name="catlexception"></a>CAtlException::CAtlException

コンストラクターです。

```cpp
CAtlException(HRESULT hr) throw();
CAtlException() throw();
```

### <a name="parameters"></a>パラメーター

*hr*<br/>
HRESULT エラー コード。

## <a name="catlexceptionoperator-hresult"></a><a name="operator_hresult"></a>CAtlException:: operator HRESULT

現在のオブジェクトを HRESULT 値にキャストします。

```cpp
operator HRESULT() const throw ();
```

## <a name="catlexceptionm_hr"></a><a name="m_hr"></a>CAtlException:: m_hr

HRESULT データメンバー。

```cpp
HRESULT m_hr;
```

### <a name="remarks"></a>解説

エラー状態を格納するデータメンバー。 HRESULT 値は、コンストラクター [CAtlException:: CAtlException](#catlexception)によって設定されます。

## <a name="see-also"></a>関連項目

[AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
