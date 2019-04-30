---
title: ITopologyNode 構造体
ms.date: 11/04/2016
f1_keywords:
- ITopologyNode
- CONCRTRM/concurrency::ITopologyNode
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetExecutionResourceCount
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetFirstExecutionResource
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetId
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNext
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNumaNode
helpviewer_keywords:
- ITopologyNode structure
ms.assetid: 92e7e032-04f6-4c7c-be36-8f9a35fc4734
ms.openlocfilehash: 867e0543d1b9f2810a3fe761f038947c4d88da4d
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346216"
---
# <a name="itopologynode-structure"></a>ITopologyNode 構造体

リソース マネージャーで定義されるトポロジ ノードへのインターフェイスです。 ノードには 1 つ以上の実行リソースが含まれます。

## <a name="syntax"></a>構文

```
struct ITopologyNode;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ITopologyNode::GetExecutionResourceCount](#getexecutionresourcecount)|このノードでグループ化の実行リソースの数を返します。|
|[ITopologyNode::GetFirstExecutionResource](#getfirstexecutionresource)|列挙の順番でこのノードの下にグループ化された最初の実行リソースを返します。|
|[ITopologyNode::GetId](#getid)|このノードのリソース マネージャーの一意の識別子を返します。|
|[ITopologyNode::GetNext](#getnext)|列挙の順番で次のトポロジのノードにインターフェイスを返します。|
|[ITopologyNode::GetNumaNode](#getnumanode)|Windows が割り当てた、このリソース マネージャー ノードが属する、NUMA ノードの数を返します。|

## <a name="remarks"></a>Remarks

このインターフェイスは、リソース マネージャーで見られたものと、システムのトポロジを通常使用されます。

## <a name="inheritance-hierarchy"></a>継承階層

`ITopologyNode`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrtrm.h

**名前空間:** concurrency

##  <a name="getexecutionresourcecount"></a>  Itopologynode::getexecutionresourcecount メソッド

このノードでグループ化の実行リソースの数を返します。

```
virtual unsigned int GetExecutionResourceCount() const = 0;
```

### <a name="return-value"></a>戻り値

リソースの実行の数は、このノードの下一緒にグループ化します。

##  <a name="getfirstexecutionresource"></a>  Itopologynode::getfirstexecutionresource メソッド

列挙の順番でこのノードの下にグループ化された最初の実行リソースを返します。

```
virtual ITopologyExecutionResource *GetFirstExecutionResource() const = 0;
```

### <a name="return-value"></a>戻り値

列挙の順番でこのノードの下に最初の実行リソースがグループ化されます。

##  <a name="getid"></a>  Itopologynode::getid メソッド

このノードのリソース マネージャーの一意の識別子を返します。

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>戻り値

このノードのリソース マネージャーの一意の識別子。

### <a name="remarks"></a>Remarks

同時実行ランタイムでは、プロセッサのノードのグループで、システム上のハードウェア スレッドを表します。 ノードは、通常、システムのハードウェア トポロジから派生します。 たとえば、特定のソケットまたは特定の NUMA ノードのすべてのプロセッサが同一プロセッサ ノードに属している可能性があります。 Resource Manager では、以降ではこれらのノードに一意の識別子を割り当てます`0`まで`nodeCount - 1`ここで、`nodeCount`システム上のプロセッサ ノードの合計数を表します。

ノードの数は、関数から取得できます[GetProcessorNodeCount](concurrency-namespace-functions.md)します。

##  <a name="getnext"></a>  Itopologynode::getnext メソッド

列挙の順番で次のトポロジのノードにインターフェイスを返します。

```
virtual ITopologyNode *GetNext() const = 0;
```

### <a name="return-value"></a>戻り値

列挙の順番で次のノードへのインターフェイス。 このメソッドが値を返すシステム トポロジの列挙の順番にないノードがある場合`NULL`します。

##  <a name="getnumanode"></a>  Itopologynode::getnumanode メソッド

Windows が割り当てた、このリソース マネージャー ノードが属する、NUMA ノードの数を返します。

```
virtual unsigned long GetNumaNode() const = 0;
```

### <a name="return-value"></a>戻り値

Windows が割り当てた、このリソース マネージャー ノードが属する、NUMA ノードの数。

### <a name="remarks"></a>Remarks

このノードに属する仮想プロセッサ ルートで実行中のスレッド プロキシは、このメソッドが返す NUMA ノードに、少なくとも NUMA ノードのレベルで関係があります。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)
