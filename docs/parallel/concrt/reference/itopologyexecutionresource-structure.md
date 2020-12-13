---
description: 詳細については、「ITopologyExecutionResource 構造」を参照してください。
title: ITopologyExecutionResource 構造体
ms.date: 11/04/2016
f1_keywords:
- ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetId
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetNext
helpviewer_keywords:
- ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
ms.openlocfilehash: c2567cf9e34e0b27308e331056d5e0dbc99b2779
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334375"
---
# <a name="itopologyexecutionresource-structure"></a>ITopologyExecutionResource 構造体

リソース マネージャーで定義される実行リソースへのインターフェイスです。

## <a name="syntax"></a>構文

```cpp
struct ITopologyExecutionResource;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ITopologyExecutionResource:: GetId](#getid)|この実行リソースのリソースマネージャーの一意の識別子を返します。|
|[ITopologyExecutionResource:: GetNext](#getnext)|列挙の順序で次の実行リソースへのインターフェイスを返します。|

## <a name="remarks"></a>解説

このインターフェイスは、通常、リソースマネージャーによって監視されるシステムのトポロジを調べるために使用されます。

## <a name="inheritance-hierarchy"></a>継承階層

`ITopologyExecutionResource`

## <a name="requirements"></a>要件

**ヘッダー:** concrtrm. h

**名前空間:** concurrency

## <a name="itopologyexecutionresourcegetid-method"></a><a name="getid"></a> ITopologyExecutionResource:: GetId メソッド

この実行リソースのリソースマネージャーの一意の識別子を返します。

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>戻り値

この実行リソースのリソースマネージャーの一意の識別子。

## <a name="itopologyexecutionresourcegetnext-method"></a><a name="getnext"></a> ITopologyExecutionResource:: GetNext メソッド

列挙の順序で次の実行リソースへのインターフェイスを返します。

```cpp
virtual ITopologyExecutionResource *GetNext() const = 0;
```

### <a name="return-value"></a>戻り値

列挙順序での次の実行リソースへのインターフェイス。 この実行リソースが属しているノードの列挙順序にノードがそれ以上ない場合、このメソッドは値を返し `NULL` ます。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)
