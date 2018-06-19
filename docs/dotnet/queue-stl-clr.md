---
title: キュー (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::queue
dev_langs:
- C++
helpviewer_keywords:
- <queue> header [STL/CLR]
- queue class [STL/CLR]
- <cliext/queue> header [STL/CLR]
ms.assetid: 9ea7dec3-ea98-48ff-87d0-a5afc924aaf2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7e65d5a364f5886df2bad976e3c34dc57266b70f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33172745"
---
# <a name="queue-stlclr"></a>queue (STL/CLR)
このテンプレート クラスでは、先入れ先出しのアクセス権を持つ要素の可変長シーケンスを制御するオブジェクトについて説明します。 コンテナー アダプターを使用する`queue`キューとしてを基になるコンテナーを管理します。  
  
 下記に、`GValue`と同じ`Value`ref 型を後者には、しない限り、どのケースでは`Value^`します。 同様に、`GContainer`と同じ`Container`ref 型を後者には、しない限り、どのケースでは`Container^`します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Value,  
    typename Container>  
    ref class queue  
        :   public  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IQueue<GValue, GContainer>  
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
|[queue::const_reference (STL/CLR)](../dotnet/queue-const-reference-stl-clr.md)|要素への定数参照の型です。|  
|[queue::container_type (STL/CLR)](../dotnet/queue-container-type-stl-clr.md)|基になるコンテナーの型。|  
|[queue::difference_type (STL/CLR)](../dotnet/queue-difference-type-stl-clr.md)|2 つの要素間の距離を表す、符号付きの型です。|  
|[queue::generic_container (STL/CLR)](../dotnet/queue-generic-container-stl-clr.md)|コンテナー アダプターのジェネリック インターフェイスの型。|  
|[queue::generic_value (STL/CLR)](../dotnet/queue-generic-value-stl-clr.md)|コンテナー アダプターのジェネリック インターフェイスの要素の型。|  
|[queue::reference (STL/CLR)](../dotnet/queue-reference-stl-clr.md)|要素への参照の型です。|  
|[queue::size_type (STL/CLR)](../dotnet/queue-size-type-stl-clr.md)|2 つの要素間の距離を表す、符号付きの型です。|  
|[queue::value_type (STL/CLR)](../dotnet/queue-value-type-stl-clr.md)|要素の型。|  
  
|メンバー関数|説明|  
|---------------------|-----------------|  
|[queue::assign (STL/CLR)](../dotnet/queue-assign-stl-clr.md)|すべての要素を置換します。|  
|[queue::back (STL/CLR)](../dotnet/queue-back-stl-clr.md)|最後の要素にアクセスします。|  
|[queue::empty (STL/CLR)](../dotnet/queue-empty-stl-clr.md)|要素が存在しないかどうかをテストします。|  
|[queue::front (STL/CLR)](../dotnet/queue-front-stl-clr.md)|最初の要素にアクセスします。|  
|[queue::get_container (STL/CLR)](../dotnet/queue-get-container-stl-clr.md)|基になるコンテナーにアクセスします。|  
|[queue::pop (STL/CLR)](../dotnet/queue-pop-stl-clr.md)|最初の要素を削除します。|  
|[queue::push (STL/CLR)](../dotnet/queue-push-stl-clr.md)|新しい最後の要素を追加します。|  
|[queue::queue (STL/CLR)](../dotnet/queue-queue-stl-clr.md)|コンテナー オブジェクトを構築します。|  
|[queue::size (STL/CLR)](../dotnet/queue-size-stl-clr.md)|要素の数をカウントします。|  
|[queue::to_array (STL/CLR)](../dotnet/queue-to-array-stl-clr.md)|被制御シーケンスを新しい配列にコピーします。|  
  
|プロパティ|説明|  
|--------------|-----------------|  
|[queue::back_item (STL/CLR)](../dotnet/queue-back-item-stl-clr.md)|最後の要素にアクセスします。|  
|[queue::front_item (STL/CLR)](../dotnet/queue-front-item-stl-clr.md)|最初の要素にアクセスします。|  
  
|演算子|説明|  
|--------------|-----------------|  
|[queue::operator= (STL/CLR)](../dotnet/queue-operator-assign-stl-clr.md)|被制御シーケンスを置き換えます。|  
|[operator!= (queue) (STL/CLR)](../dotnet/operator-inequality-queue-stl-clr.md)|かどうかを`queue`オブジェクトが他と等しくない`queue`オブジェクト。|  
|[operator< (queue) (STL/CLR)](../dotnet/operator-less-than-queue-stl-clr.md)|かどうかを`queue`オブジェクトが他よりも小さい`queue`オブジェクト。|  
|[operator<= (queue) (STL/CLR)](../dotnet/operator-less-or-equal-queue-stl-clr.md)|かどうかを`queue`オブジェクトが別に小さい`queue`オブジェクト。|  
|[operator== (queue) (STL/CLR)](../dotnet/operator-equality-queue-stl-clr.md)|かどうかを`queue`オブジェクトが他と等しい`queue`オブジェクト。|  
|[operator> (queue) (STL/CLR)](../dotnet/operator-greater-than-queue-stl-clr.md)|かどうかを`queue`オブジェクトが他よりも大きい`queue`オブジェクト。|  
|[operator>= (queue) (STL/CLR)](../dotnet/operator-greater-or-equal-queue-stl-clr.md)|かどうかを`queue`オブジェクトがより大きいか等しい間`queue`オブジェクト。|  
  
## <a name="interfaces"></a>インターフェイス  
  
|Interface|説明|  
|---------------|-----------------|  
|<xref:System.ICloneable>|オブジェクトが重複してください。|  
|I キュー\<値、コンテナー >|汎用的なコンテナーのアダプターを管理します。|  
  
## <a name="remarks"></a>コメント  
 オブジェクトは、割り当てし、型の基になるコンテナーを制御するシーケンスの記憶域を解放`Container`、格納する`Value`要素および要求時に増加します。 オブジェクトが最初の要素を押すだけへのアクセスを制限し、(FIFO キューまたはキューでは単とも呼ばれます) キューの最後の要素をポップ、先入れ先出しの実装します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/キュー >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [一覧 (STL/CLR)](../dotnet/list-stl-clr.md)   
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [スタック (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [ベクトル (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [STL/CLR ライブラリ リファレンス](../dotnet/stl-clr-library-reference.md)