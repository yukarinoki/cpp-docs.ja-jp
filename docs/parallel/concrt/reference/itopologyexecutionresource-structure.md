---
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
ms.openlocfilehash: 2c9221cab1ac2d48bd099a769188e4bee797823c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368145"
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
|[リソースを実行します。](#getid)|この実行リソースのリソース マネージャーの一意の識別子を返します。|
|[次のリソースを取得します。](#getnext)|次の実行リソースへのインターフェイスを列挙順に返します。|

## <a name="remarks"></a>解説

このインターフェイスは、通常、リソース マネージャーによって監視されるシステムのトポロジをウォークするために使用されます。

## <a name="inheritance-hierarchy"></a>継承階層

`ITopologyExecutionResource`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrtrm.h

**名前空間:** 同時実行

## <a name="itopologyexecutionresourcegetid-method"></a><a name="getid"></a>メソッドを実行します。

この実行リソースのリソース マネージャーの一意の識別子を返します。

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>戻り値

この実行リソースのリソース マネージャーの一意の識別子。

## <a name="itopologyexecutionresourcegetnext-method"></a><a name="getnext"></a>次のメソッドを取得します。

次の実行リソースへのインターフェイスを列挙順に返します。

```cpp
virtual ITopologyExecutionResource *GetNext() const = 0;
```

### <a name="return-value"></a>戻り値

列挙順で、次の実行リソースへのインターフェイス。 この実行リソースが属するノードの列挙順にノードが存在しない場合、このメソッドは値`NULL`を返します。

## <a name="see-also"></a>関連項目

[同時実行名前空間](concurrency-namespace.md)
