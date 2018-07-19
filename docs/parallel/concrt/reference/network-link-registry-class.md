---
title: network_link_registry クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- network_link_registry
- AGENTS/concurrency::network_link_registry
- AGENTS/concurrency::network_link_registry::add
- AGENTS/concurrency::network_link_registry::begin
- AGENTS/concurrency::network_link_registry::contains
- AGENTS/concurrency::network_link_registry::count
- AGENTS/concurrency::network_link_registry::remove
dev_langs:
- C++
helpviewer_keywords:
- network_link_registry class
ms.assetid: 3e7b4097-09f1-4252-964e-b15b8f7f7fc6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dab0ad6aff391eb89ac59198fb8c173ecb362bbd
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688298"
---
# <a name="networklinkregistry-class"></a>network_link_registry クラス
`network_link_registry` 抽象基底クラスによって、ソース ブロックとターゲット ブロック間のリンクを管理します。  
  
## <a name="syntax"></a>構文  
  
```
template<class _Block>
class network_link_registry;
```  
  
#### <a name="parameters"></a>パラメーター  
 `_Block`  
 ブロックのデータ型に格納されている、`network_link_registry`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`const_pointer`|ポインターを提供する型、`const`内の要素、`network_link_registry`オブジェクト。|  
|`const_reference`|参照を提供する型、`const`に要素が格納されている、`network_link_registry`読み取りや、const の操作を実行するオブジェクト。|  
|`iterator`|反復子を提供する型の読み取りまたはの任意の要素を変更できる、`network_link_registry`オブジェクト。|  
|`type`|格納されているブロックの型を表す型、`network_link_registry`オブジェクト。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[add](#add)|派生クラスでオーバーライドされるへのリンクを追加、`network_link_registry`オブジェクト。|  
|[begin](#begin)|派生クラスでオーバーライドされると、反復子を返しますの最初の要素を`network_link_registry`オブジェクト。|  
|[contains](#contains)|派生クラスでオーバーライドされると、検索、`network_link_registry`の指定されたブロックのオブジェクト。|  
|[count](#count)|派生クラスでオーバーライドされると、内の項目の数を返します、`network_link_registry`オブジェクト。|  
|[remove](#remove)|派生クラスでオーバーライドされると、削除、指定されたブロックから、`network_link_registry`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 `network link registry`の同時アクセスの安全ではありません。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `network_link_registry`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="add"></a> 追加 

 派生クラスでオーバーライドされるへのリンクを追加、`network_link_registry`オブジェクト。  
  
```
virtual void add(_EType _Link) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Link`  
 追加されるブロックへのポインター。  
  
##  <a name="begin"></a> 開始 

 派生クラスでオーバーライドされると、反復子を返しますの最初の要素を`network_link_registry`オブジェクト。  
  
```
virtual iterator begin() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 最初の要素を指定する反復子、`network_link_registry`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 によって、反復子の最終の状態が示される、`NULL`リンクします。  
  
##  <a name="contains"></a> 含まれています 

 派生クラスでオーバーライドされると、検索、`network_link_registry`の指定されたブロックのオブジェクト。  
  
```
virtual bool contains(_EType _Link) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Link`  
 検索対象となるブロックへのポインター、`network_link_registry`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `true` ブロックが見つかった場合は`false`それ以外の場合。  
  
##  <a name="count"></a> カウント 

 派生クラスでオーバーライドされると、内の項目の数を返します、`network_link_registry`オブジェクト。  
  
```
virtual size_t count() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 内の項目数、`network_link_registry`オブジェクト。  
  
##  <a name="remove"></a> 削除します。 

 派生クラスでオーバーライドされると、削除、指定されたブロックから、`network_link_registry`オブジェクト。  
  
```
virtual bool remove(_EType _Link) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Link`  
 削除する場合はブロックへのポインターが見つかりました。  
  
### <a name="return-value"></a>戻り値  
 `true` リンクが検出され、削除、`false`それ以外の場合。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [single_link_registry クラス](single-link-registry-class.md)   
 [multi_link_registry クラス](multi-link-registry-class.md)
