---
description: '詳細情報: CAtlException クラス'
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
ms.openlocfilehash: b6d788bc8d852fa0b8d091682ff7740aa4ebbbed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147473"
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

オブジェクトは、 `CAtlException` ATL 操作に関連する例外条件を表します。 クラスには、 `CAtlException` 例外の理由を示すステータスコードを格納するパブリックデータメンバーと、例外を HRESULT として扱うことができるキャスト演算子が含まれています。

一般に、 `AtlThrow` オブジェクトを直接作成するのではなく、を呼び出し `CAtlException` ます。

## <a name="requirements"></a>要件

**ヘッダー:** atlexcept. h

## <a name="catlexceptioncatlexception"></a><a name="catlexception"></a> CAtlException::CAtlException

コンストラクターです。

```cpp
CAtlException(HRESULT hr) throw();
CAtlException() throw();
```

### <a name="parameters"></a>パラメーター

*時間*<br/>
HRESULT エラー コード。

## <a name="catlexceptionoperator-hresult"></a><a name="operator_hresult"></a> CAtlException:: operator HRESULT

現在のオブジェクトを HRESULT 値にキャストします。

```cpp
operator HRESULT() const throw ();
```

## <a name="catlexceptionm_hr"></a><a name="m_hr"></a> CAtlException:: m_hr

HRESULT データメンバー。

```cpp
HRESULT m_hr;
```

### <a name="remarks"></a>解説

エラー状態を格納するデータメンバー。 HRESULT 値は、コンストラクター [CAtlException:: CAtlException](#catlexception)によって設定されます。

## <a name="see-also"></a>関連項目

[AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
