---
title: スタック (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::stack
dev_langs:
- C++
helpviewer_keywords:
- <stack> header [STL/CLR]
- <cliext/stack> header [STL/CLR]
- stack class [STL/CLR]
ms.assetid: 6ee96b9f-8a33-4cf7-b7e0-6535c24bdefb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 290857b51fea6726ec7e4a836d4afe1b33a8e615
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="stack-stlclr"></a>stack (STL/CLR)
このテンプレート クラスでは、後入れ先出しのアクセス権を持つ要素の可変長シーケンスを制御するオブジェクトについて説明します。 コンテナー アダプターを使用する`stack`プッシュ ダウン スタックとの基になるコンテナーを管理します。  
  
 下記に、`GValue`と同じ`Value`ref 型を後者には、しない限り、どのケースでは`Value^`します。 同様に、`GContainer`と同じ`Container`ref 型を後者には、しない限り、どのケースでは`Container^`します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Value,  
    typename Container>  
    ref class stack  
        :   public  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IStack<GValue, GContainer>  
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
|[stack::const_reference (STL/CLR)](../dotnet/stack-const-reference-stl-clr.md)|要素への定数参照の型です。|  
|[stack::container_type (STL/CLR)](../dotnet/stack-container-type-stl-clr.md)|基になるコンテナーの型。|  
|[stack::difference_type (STL/CLR)](../dotnet/stack-difference-type-stl-clr.md)|2 つの要素間の距離を表す、符号付きの型です。|  
|[stack::generic_container (STL/CLR)](../dotnet/stack-generic-container-stl-clr.md)|コンテナー アダプターのジェネリック インターフェイスの型。|  
|[stack::generic_value (STL/CLR)](../dotnet/stack-generic-value-stl-clr.md)|コンテナー アダプターのジェネリック インターフェイスの要素の型。|  
|[stack::reference (STL/CLR)](../dotnet/stack-reference-stl-clr.md)|要素への参照の型です。|  
|[stack::size_type (STL/CLR)](../dotnet/stack-size-type-stl-clr.md)|2 つの要素間の距離を表す、符号付きの型です。|  
|[stack::value_type (STL/CLR)](../dotnet/stack-value-type-stl-clr.md)|要素の型。|  
  
|メンバー関数|説明|  
|---------------------|-----------------|  
|[stack::assign (STL/CLR)](../dotnet/stack-assign-stl-clr.md)|すべての要素を置換します。|  
|[stack::empty (STL/CLR)](../dotnet/stack-empty-stl-clr.md)|要素が存在しないかどうかをテストします。|  
|[stack::get_container (STL/CLR)](../dotnet/stack-get-container-stl-clr.md)|基になるコンテナーにアクセスします。|  
|[stack::pop (STL/CLR)](../dotnet/stack-pop-stl-clr.md)|最後の要素を削除します。|  
|[stack::push (STL/CLR)](../dotnet/stack-push-stl-clr.md)|新しい最後の要素を追加します。|  
|[stack::size (STL/CLR)](../dotnet/stack-size-stl-clr.md)|要素の数をカウントします。|  
|[stack::stack (STL/CLR)](../dotnet/stack-stack-stl-clr.md)|コンテナー オブジェクトを構築します。|  
|[stack::top (STL/CLR)](../dotnet/stack-top-stl-clr.md)|最後の要素にアクセスします。|  
|[stack::to_array (STL/CLR)](../dotnet/stack-to-array-stl-clr.md)|被制御シーケンスを新しい配列にコピーします。|  
  
|プロパティ|説明|  
|--------------|-----------------|  
|[stack::top_item (STL/CLR)](../dotnet/stack-top-item-stl-clr.md)|最後の要素にアクセスします。|  
  
|演算子|説明|  
|--------------|-----------------|  
|[stack::operator= (STL/CLR)](../dotnet/stack-operator-assign-stl-clr.md)|被制御シーケンスを置き換えます。|  
|[operator!= (stack) (STL/CLR)](../dotnet/operator-inequality-stack-stl-clr.md)|かどうかを`stack`オブジェクトが他と等しくない`stack`オブジェクト。|  
|[operator< (stack) (STL/CLR)](../dotnet/operator-less-than-stack-stl-clr.md)|かどうかを`stack`オブジェクトが他よりも小さい`stack`オブジェクト。|  
|[operator<= (stack) (STL/CLR)](../dotnet/operator-less-or-equal-stack-stl-clr.md)|かどうかを`stack`オブジェクトが別に小さい`stack`オブジェクト。|  
|[operator== (stack) (STL/CLR)](../dotnet/operator-equality-stack-stl-clr.md)|かどうかを`stack`オブジェクトが他と等しい`stack`オブジェクト。|  
|[operator> (stack) (STL/CLR)](../dotnet/operator-greater-than-stack-stl-clr.md)|かどうかを`stack`オブジェクトが他よりも大きい`stack`オブジェクト。|  
|[operator>= (stack) (STL/CLR)](../dotnet/operator-greater-or-equal-stack-stl-clr.md)|かどうかを`stack`オブジェクトがより大きいか等しい間`stack`オブジェクト。|  
  
## <a name="interfaces"></a>インターフェイス  
  
|Interface|説明|  
|---------------|-----------------|  
|<xref:System.ICloneable>|オブジェクトが重複してください。|  
|IStack\<値、コンテナー >|汎用的なコンテナーのアダプターを管理します。|  
  
## <a name="remarks"></a>コメント  
 オブジェクトは、割り当てし、型の基になるコンテナーを制御するシーケンスの記憶域を解放`Container`、格納する`Value`要素および要求時に増加します。 オブジェクトは、プッシュおよびポップだけの最後の要素、後入れ先出しキュー (LIFO キュー、またはスタックとも呼ばれます) の実装へのアクセスを制限します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/stack >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [一覧 (STL/CLR)](../dotnet/list-stl-clr.md)   
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [キュー (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [ベクトル (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [STL/CLR ライブラリ リファレンス](../dotnet/stl-clr-library-reference.md)