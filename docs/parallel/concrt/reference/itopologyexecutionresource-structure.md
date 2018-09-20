---
title: ITopologyExecutionResource 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetId
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetNext
dev_langs:
- C++
helpviewer_keywords:
- ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60a0097aded73e3e0251d38daf5da71197668d3a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383793"
---
# <a name="itopologyexecutionresource-structure"></a>ITopologyExecutionResource 構造体

リソース マネージャーで定義される実行リソースへのインターフェイスです。

## <a name="syntax"></a>構文

```
struct ITopologyExecutionResource;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ITopologyExecutionResource::GetId](#getid)|この実行リソースのリソース マネージャーの一意の識別子を返します。|
|[ITopologyExecutionResource::GetNext](#getnext)|列挙の順番で次の実行リソースへのインターフェイスを返します。|

## <a name="remarks"></a>Remarks

このインターフェイスは、リソース マネージャーで見られたものと、システムのトポロジを通常使用されます。

## <a name="inheritance-hierarchy"></a>継承階層

`ITopologyExecutionResource`

## <a name="requirements"></a>要件

**ヘッダー:** concrtrm.h

**名前空間:** concurrency

##  <a name="getid"></a>  Itopologyexecutionresource::getid メソッド

この実行リソースのリソース マネージャーの一意の識別子を返します。

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>戻り値

この実行リソースのリソース マネージャーの一意の識別子。

##  <a name="getnext"></a>  Itopologyexecutionresource::getnext メソッド

列挙の順番で次の実行リソースへのインターフェイスを返します。

```
virtual ITopologyExecutionResource *GetNext() const = 0;
```

### <a name="return-value"></a>戻り値

列挙の順番で、次の実行リソースへのインターフェイス。 このメソッドが値を返す場合、この実行リソースが所属するノードの列挙の順番に複数のノードがありませんが、`NULL`します。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)
