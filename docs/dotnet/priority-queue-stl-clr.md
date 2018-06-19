---
title: priority_queue (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::priority_queue
dev_langs:
- C++
helpviewer_keywords:
- priority_queue class [STL/CLR]
- <queue> header [STL/CLR]
- <cliext/queue> header [STL/CLR]
ms.assetid: 4d0000d3-68ff-4c4b-8157-7060540136f5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 63e806603a795a71dc2afb95ae17779d1c6f210b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33172541"
---
# <a name="priorityqueue-stlclr"></a>priority_queue (STL/CLR)
このテンプレート クラスは、可変長のアクセスが制限されている要素のシーケンスを順序付けを制御するオブジェクトについて説明します。 コンテナー アダプターを使用する`priority_queue`優先度のキューとしてを基になるコンテナーを管理します。  
  
 下記に、`GValue`と同じ`Value`ref 型を後者には、しない限り、どのケースでは`Value^`します。 同様に、`GContainer`と同じ`Container`ref 型を後者には、しない限り、どのケースでは`Container^`します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Value,  
    typename Container>  
    ref class priority_queue  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IPriorityQueue<GValue, GContainer>  
    { ..... };  
```  
  
#### <a name="parameters"></a>パラメーター  
 [値]  
 被制御シーケンス内の要素の型。  
  
 コンテナー  
 基になるコンテナーの型。  
  
## <a name="members"></a>メンバー  
  
|型定義|説明|  
|---------------------|-----------------|  
|[priority_queue::const_reference (STL/CLR)](../dotnet/priority-queue-const-reference-stl-clr.md)|要素への定数参照の型です。|  
|[priority_queue::container_type (STL/CLR)](../dotnet/priority-queue-container-type-stl-clr.md)|基になるコンテナーの型。|  
|[priority_queue::difference_type (STL/CLR)](../dotnet/priority-queue-difference-type-stl-clr.md)|2 つの要素間の距離を表す、符号付きの型です。|  
|[priority_queue::generic_container (STL/CLR)](../dotnet/priority-queue-generic-container-stl-clr.md)|コンテナー アダプターのジェネリック インターフェイスの型。|  
|[priority_queue::generic_value (STL/CLR)](../dotnet/priority-queue-generic-value-stl-clr.md)|コンテナー アダプターのジェネリック インターフェイスの要素の型。|  
|[priority_queue::reference (STL/CLR)](../dotnet/priority-queue-reference-stl-clr.md)|要素への参照の型です。|  
|[priority_queue::size_type (STL/CLR)](../dotnet/priority-queue-size-type-stl-clr.md)|2 つの要素間の距離を表す、符号付きの型です。|  
|[priority_queue::value_compare (STL/CLR)](../dotnet/priority-queue-value-compare-stl-clr.md)|2 つの要素の順序付けのデリゲート。|  
|[priority_queue::value_type (STL/CLR)](../dotnet/priority-queue-value-type-stl-clr.md)|要素の型。|  
  
|メンバー関数|説明|  
|---------------------|-----------------|  
|[priority_queue::assign (STL/CLR)](../dotnet/priority-queue-assign-stl-clr.md)|すべての要素を置換します。|  
|[priority_queue::empty (STL/CLR)](../dotnet/priority-queue-empty-stl-clr.md)|要素が存在しないかどうかをテストします。|  
|[priority_queue::get_container (STL/CLR)](../dotnet/priority-queue-get-container-stl-clr.md)|基になるコンテナーにアクセスします。|  
|[priority_queue::pop (STL/CLR)](../dotnet/priority-queue-pop-stl-clr.md)|Hghest 優先度要素を削除します。|  
|[priority_queue::priority_queue (STL/CLR)](../dotnet/priority-queue-priority-queue-stl-clr.md)|コンテナー オブジェクトを構築します。|  
|[priority_queue::push (STL/CLR)](../dotnet/priority-queue-push-stl-clr.md)|新しい要素を追加します。|  
|[priority_queue::size (STL/CLR)](../dotnet/priority-queue-size-stl-clr.md)|要素の数をカウントします。|  
|[priority_queue::top (STL/CLR)](../dotnet/priority-queue-top-stl-clr.md)|最も高い優先順位の要素にアクセスします。|  
|[priority_queue::to_array (STL/CLR)](../dotnet/priority-queue-to-array-stl-clr.md)|被制御シーケンスを新しい配列にコピーします。|  
|[priority_queue::value_comp (STL/CLR)](../dotnet/priority-queue-value-comp-stl-clr.md)|2 つの要素の順序付けのデリゲートをコピーします。|  
  
|プロパティ|説明|  
|--------------|-----------------|  
|[priority_queue::top_item (STL/CLR)](../dotnet/priority-queue-top-item-stl-clr.md)|最も高い優先順位の要素にアクセスします。|  
  
|演算子|説明|  
|--------------|-----------------|  
|[priority_queue::operator= (STL/CLR)](../dotnet/priority-queue-operator-assign-stl-clr.md)|被制御シーケンスを置き換えます。|  
  
## <a name="interfaces"></a>インターフェイス  
  
|Interface|説明|  
|---------------|-----------------|  
|<xref:System.ICloneable>|オブジェクトが重複してください。|  
|IPriorityQueue\<値、コンテナー >|汎用的なコンテナーのアダプターを管理します。|  
  
## <a name="remarks"></a>コメント  
 オブジェクトは、割り当てし、型の基になるコンテナーを制御するシーケンスの記憶域を解放`Container`、格納する`Value`要素および要求時に増加します。 アクセスとリムーバブル最も高い優先度要素 (最上位の要素) を持つ、ヒープとして順序付けられたシーケンスを保持します。 オブジェクトは、新しい要素をプッシュおよびポップだけでは、最も高い優先度要素優先度のキューの実装へのアクセスを制限します。  
  
 オブジェクトがストアド デリゲート型のオブジェクトを呼び出すことによって、制御するシーケンスを並べ替えます[priority_queue::value_compare (STL/CLR)](../dotnet/priority-queue-value-compare-stl-clr.md)です。 Priority_queue; を作成する場合は、ストアド デリゲート オブジェクトを指定することができます。デリゲート オブジェクトを指定しないと、既定値が比較`operator<(value_type, value_type)`です。 このメンバー関数を呼び出すことによってこのストアド オブジェクトにアクセスする[priority_queue::value_comp (STL/CLR)](../dotnet/priority-queue-value-comp-stl-clr.md)`()`です。  
  
 このようなデリゲート オブジェクト必要があります、厳密弱順序強制型の値で[priority_queue::value_type (STL/CLR)](../dotnet/priority-queue-value-type-stl-clr.md)です。 つまり、任意の 2 つのキーの`X`と`Y`:  
  
 `value_comp()(X, Y)` すべての呼び出しでブール値を同じ結果を返します。  
  
 場合`value_comp()(X, Y)`が true の場合、 `value_comp()(Y, X)` false である必要があります。  
  
 場合`value_comp()(X, Y)`が true の場合、`X`をする前に並べ替えるといいます`Y`です。  
  
 場合`!value_comp()(X, Y) && !value_comp()(Y, X)`が true の場合、`X`と`Y`大小関係が等しいと呼ばれます。  
  
 任意の要素に対して`X`の直前まで`Y`、被制御シーケンスの`key_comp()(Y, X)`は false。 (既定のデリゲート オブジェクトのキーしない値が減少します。)  
  
 最高の優先順位の要素は、その他の要素の前に順序付けされていない先の要素のいずれかでは、です。  
  
 基になるコンテナーでは、要素の順序に並べたヒープとして残される: ため  
  
 コンテナーは、ランダム アクセス反復子をサポートする必要があります。  
  
 同じ順序で要素は、プッシュされたよりも、異なる順序でポップ可能性があります。 (順序付けが安定しない。)  
  
 したがって、候補となる、基になるコンテナーを含める[deque (STL/CLR)](../dotnet/deque-stl-clr.md)と[ベクター (STL/CLR)](../dotnet/vector-stl-clr.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/キュー >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [キュー (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [スタック (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [ベクトル (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [STL/CLR ライブラリ リファレンス](../dotnet/stl-clr-library-reference.md)