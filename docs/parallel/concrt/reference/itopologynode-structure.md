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
ms.openlocfilehash: 7cb815c4f7dc5ad09e8d352abc3f3375b8d9e205
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368102"
---
# <a name="itopologynode-structure"></a>ITopologyNode 構造体

リソース マネージャーで定義されるトポロジ ノードへのインターフェイスです。 ノードには 1 つ以上の実行リソースが含まれます。

## <a name="syntax"></a>構文

```cpp
struct ITopologyNode;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ノード::実行リソースカウント](#getexecutionresourcecount)|このノードの下でグループ化された実行リソースの数を返します。|
|[ノード::最初の実行リソースを取得します。](#getfirstexecutionresource)|このノードの下でグループ化された最初の実行リソースを列挙順で返します。|
|[トポロジ ノード::取得ID](#getid)|このノードのリソース マネージャーの一意の識別子を返します。|
|[次のノードを取得します。](#getnext)|次のトポロジ ノードへのインターフェイスを列挙順に返します。|
|[イトトポロジノード::GetNumaNode](#getnumanode)|Windows が割り当てた、このリソース マネージャー ノードが属する、NUMA ノードの数を返します。|

## <a name="remarks"></a>解説

このインターフェイスは、通常、リソース マネージャーによって監視されるシステムのトポロジをウォークするために使用されます。

## <a name="inheritance-hierarchy"></a>継承階層

`ITopologyNode`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrtrm.h

**名前空間:** 同時実行

## <a name="itopologynodegetexecutionresourcecount-method"></a><a name="getexecutionresourcecount"></a>メソッドを取得します。

このノードの下でグループ化された実行リソースの数を返します。

```cpp
virtual unsigned int GetExecutionResourceCount() const = 0;
```

### <a name="return-value"></a>戻り値

このノードの下でグループ化された実行リソースの数。

## <a name="itopologynodegetfirstexecutionresource-method"></a><a name="getfirstexecutionresource"></a>メソッドを取得します。

このノードの下でグループ化された最初の実行リソースを列挙順で返します。

```cpp
virtual ITopologyExecutionResource *GetFirstExecutionResource() const = 0;
```

### <a name="return-value"></a>戻り値

このノードの下で列挙順にグループ化された最初の実行リソース。

## <a name="itopologynodegetid-method"></a><a name="getid"></a>メソッドを取得します。

このノードのリソース マネージャーの一意の識別子を返します。

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>戻り値

このノードのリソース マネージャーの一意の識別子。

### <a name="remarks"></a>解説

同時実行ランタイムは、プロセッサ ノードのグループでシステム上のハードウェア スレッドを表します。 ノードは通常、システムのハードウェア トポロジから派生します。 たとえば、特定のソケットまたは特定の NUMA ノード上のすべてのプロセッサが同じプロセッサ ノードに属している場合があります。 リソース マネージャは、システム上のプロセッサ ノードの合計数`0`を`nodeCount`表す、 `nodeCount - 1`( を含む ) で始まるこれらのノードに一意の識別子を割り当てます。

ノードの数は、関数[から](concurrency-namespace-functions.md)取得できます。

## <a name="itopologynodegetnext-method"></a><a name="getnext"></a>次のメソッドを取得します。

次のトポロジ ノードへのインターフェイスを列挙順に返します。

```cpp
virtual ITopologyNode *GetNext() const = 0;
```

### <a name="return-value"></a>戻り値

列挙順の次のノードへのインターフェイス。 システム トポロジの列挙順にノードが存在しない場合、このメソッドは値`NULL`を返します。

## <a name="itopologynodegetnumanode-method"></a><a name="getnumanode"></a>メソッドを取得します。

Windows が割り当てた、このリソース マネージャー ノードが属する、NUMA ノードの数を返します。

```cpp
virtual unsigned long GetNumaNode() const = 0;
```

### <a name="return-value"></a>戻り値

Windows が割り当てた、このリソース マネージャー ノードが属する、NUMA ノードの数。

### <a name="remarks"></a>解説

このノードに属する仮想プロセッサ ルートで実行中のスレッド プロキシは、このメソッドが返す NUMA ノードに、少なくとも NUMA ノードのレベルで関係があります。

## <a name="see-also"></a>関連項目

[同時実行名前空間](concurrency-namespace.md)
