---
title: ベクトル (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector
dev_langs:
- C++
helpviewer_keywords:
- vector class [STL/CLR]
- <cliext/vector> header [STL/CLR]
- <vector> header [STL/CLR]
ms.assetid: f90060d5-097a-4e9d-9a26-a634b5b9c6c2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: de5d09d569933dc06666ed2008081703d59c1564
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="vector-stlclr"></a>vector (STL/CLR)
このテンプレート クラスでは、ランダム アクセス権を持つ要素の可変長シーケンスを制御するオブジェクトについて説明します。 コンテナーを使用する`vector`ストレージの連続ブロックとして要素のシーケンスを管理します。 ブロックは、必要に応じて大きくを配列として実装されます。  
  
 下記に、`GValue`と同じ`Value`ref 型を後者には、しない限り、どのケースでは`Value^`します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Value>  
    ref class vector  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IVector<GValue>  
    { ..... };  
```  
  
#### <a name="parameters"></a>パラメーター  
 [値]  
 被制御シーケンス内の要素の型。  
  
## <a name="members"></a>メンバー  
  
|型定義|説明|  
|---------------------|-----------------|  
|[vector::const_iterator (STL/CLR)](../dotnet/vector-const-iterator-stl-clr.md)|被制御シーケンスの定数反復子の型です。|  
|[vector::const_reference (STL/CLR)](../dotnet/vector-const-reference-stl-clr.md)|要素への定数参照の型です。|  
|[vector::const_reverse_iterator (STL/CLR)](../dotnet/vector-const-reverse-iterator-stl-clr.md)|被制御シーケンスの定数反転反復子の型です。|  
|[vector::difference_type (STL/CLR)](../dotnet/vector-difference-type-stl-clr.md)|2 つの要素間の距離を表す、符号付きの型です。|  
|[vector::generic_container (STL/CLR)](../dotnet/vector-generic-container-stl-clr.md)|コンテナーのジェネリック インターフェイスの型。|  
|[vector::generic_iterator (STL/CLR)](../dotnet/vector-generic-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反復子の型。|  
|[vector::generic_reverse_iterator (STL/CLR)](../dotnet/vector-generic-reverse-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反転反復子の型。|  
|[vector::generic_value (STL/CLR)](../dotnet/vector-generic-value-stl-clr.md)|コンテナーのジェネリック インターフェイスの要素の型。|  
|[vector::iterator (STL/CLR)](../dotnet/vector-iterator-stl-clr.md)|被制御シーケンスの反復子の型です。|  
|[vector::reference (STL/CLR)](../dotnet/vector-reference-stl-clr.md)|要素への参照の型です。|  
|[vector::reverse_iterator (STL/CLR)](../dotnet/vector-reverse-iterator-stl-clr.md)|被制御シーケンスの反転反復子の型です。|  
|[vector::size_type (STL/CLR)](../dotnet/vector-size-type-stl-clr.md)|2 つの要素間の距離を表す、符号付きの型です。|  
|[vector::value_type (STL/CLR)](../dotnet/vector-value-type-stl-clr.md)|要素の型。|  
  
|メンバー関数|説明|  
|---------------------|-----------------|  
|[vector::assign (STL/CLR)](../dotnet/vector-assign-stl-clr.md)|すべての要素を置換します。|  
|[vector::at (STL/CLR)](../dotnet/vector-at-stl-clr.md)|指定した位置にある要素にアクセスします。|  
|[vector::back (STL/CLR)](../dotnet/vector-back-stl-clr.md)|最後の要素にアクセスします。|  
|[vector::begin (STL/CLR)](../dotnet/vector-begin-stl-clr.md)|被制御シーケンスの先頭を指定します。|  
|[vector::capacity (STL/CLR)](../dotnet/vector-capacity-stl-clr.md)|コンテナーに割り当てられたストレージのサイズを報告します。|  
|[vector::clear (STL/CLR)](../dotnet/vector-clear-stl-clr.md)|すべての要素を削除します。|  
|[vector::empty (STL/CLR)](../dotnet/vector-empty-stl-clr.md)|要素が存在しないかどうかをテストします。|  
|[vector::end (STL/CLR)](../dotnet/vector-end-stl-clr.md)|被制御シーケンスの末尾を指定します。|  
|[vector::erase (STL/CLR)](../dotnet/vector-erase-stl-clr.md)|指定した位置にある要素を削除します。|  
|[vector::front (STL/CLR)](../dotnet/vector-front-stl-clr.md)|最初の要素にアクセスします。|  
|[vector::insert (STL/CLR)](../dotnet/vector-insert-stl-clr.md)|指定した位置にある要素を追加します。|  
|[vector::pop_back (STL/CLR)](../dotnet/vector-pop-back-stl-clr.md)|最後の要素を削除します。|  
|[vector::push_back (STL/CLR)](../dotnet/vector-push-back-stl-clr.md)|新しい最後の要素を追加します。|  
|[vector::rbegin (STL/CLR)](../dotnet/vector-rbegin-stl-clr.md)|反転被制御シーケンスの先頭を指定します。|  
|[vector::rend (STL/CLR)](../dotnet/vector-rend-stl-clr.md)|反転被制御シーケンスの末尾を指定します。|  
|[vector::reserve (STL/CLR)](../dotnet/vector-reserve-stl-clr.md)|コンテナーの容量の最小の増加のことを確認します。|  
|[vector::resize (STL/CLR)](../dotnet/vector-resize-stl-clr.md)|要素の数を変更します。|  
|[vector::size (STL/CLR)](../dotnet/vector-size-stl-clr.md)|要素の数をカウントします。|  
|[vector::swap (STL/CLR)](../dotnet/vector-swap-stl-clr.md)|2 つのコンテナーのコンテンツを交換します。|  
|[vector::to_array (STL/CLR)](../dotnet/vector-to-array-stl-clr.md)|被制御シーケンスを新しい配列にコピーします。|  
|[vector::vector (STL/CLR)](../dotnet/vector-vector-stl-clr.md)|コンテナー オブジェクトを構築します。|  
  
|プロパティ|説明|  
|--------------|-----------------|  
|[vector::back_item (STL/CLR)](../dotnet/vector-back-item-stl-clr.md)|最後の要素にアクセスします。|  
|[vector::front_item (STL/CLR)](../dotnet/vector-front-item-stl-clr.md)|最初の要素にアクセスします。|  
  
|演算子|説明|  
|--------------|-----------------|  
|[vector::operator= (STL/CLR)](../dotnet/vector-operator-assign-stl-clr.md)|被制御シーケンスを置き換えます。|  
|[vector::operator(STL/CLR)](../dotnet/vector-operator-stl-clr.md)|指定した位置にある要素にアクセスします。|  
|[operator!= (vector) (STL/CLR)](../dotnet/operator-inequality-vector-stl-clr.md)|かどうかを`vector`オブジェクトが他と等しくない`vector`オブジェクト。|  
|[operator< (vector) (STL/CLR)](../dotnet/operator-less-than-vector-stl-clr.md)|かどうかを`vector`オブジェクトが他よりも小さい`vector`オブジェクト。|  
|[operator<= (vector) (STL/CLR)](../dotnet/operator-less-or-equal-vector-stl-clr.md)|かどうかを`vector`オブジェクトが別に小さい`vector`オブジェクト。|  
|[operator== (vector) (STL/CLR)](../dotnet/operator-equality-vector-stl-clr.md)|かどうかを`vector`オブジェクトが他と等しい`vector`オブジェクト。|  
|[operator> (vector) (STL/CLR)](../dotnet/operator-greater-than-vector-stl-clr.md)|かどうかを`vector`オブジェクトが他よりも大きい`vector`オブジェクト。|  
|[operator>= (vector) (STL/CLR)](../dotnet/operator-greater-or-equal-vector-stl-clr.md)|かどうかを`vector`オブジェクトがより大きいか等しい間`vector`オブジェクト。|  
  
## <a name="interfaces"></a>インターフェイス  
  
|Interface|説明|  
|---------------|-----------------|  
|<xref:System.ICloneable>|オブジェクトが重複してください。|  
|<xref:System.Collections.IEnumerable>|要素を順番にします。|  
|<xref:System.Collections.ICollection>|要素のグループを管理します。|  
|<xref:System.Collections.Generic.IEnumerable%601>|型指定された要素を順番にします。|  
|<xref:System.Collections.Generic.ICollection%601>|型指定された要素のグループを管理します。|  
|<xref:System.Collections.Generic.IList%601>|型指定された要素の順序付きのグループを管理します。|  
|IVector < 値\>|ジェネリックなコンテナーを管理します。|  
  
## <a name="remarks"></a>コメント  
 オブジェクトは、割り当てし、ストアドの配列を制御するシーケンスの記憶域を解放`Value`要素で、必要に応じて大ききます。 拡張は、新しい要素を追加するだけのコストが償却定数時間であるような方法で発生します。 つまりの末尾に要素を追加のコストが増加せず、平均、被制御シーケンスを大きくの長さとして。 つまり、ベクトルとは、テンプレート クラスを基になるコンテナーで有力候補[スタック (STL/CLR)](../dotnet/stack-stl-clr.md)です。  
  
 A`vector`に (前) の最初の要素の 0 から数えて、数値の位置を直接指定された要素を参照できることを意味サポート ランダム アクセス反復子`size() - 1`(バックアップ) の最後の要素にします。 ベクターが基になるコンテナー テンプレート クラスに適した候補であることも意味[priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)です。  
  
 ベクターの反復子は、指定した要素のバイアスと共にその関連付けられたベクター オブジェクトへのハンドルを格納します。 反復子は、それらの関連するコンテナー オブジェクトにのみ使用できます。 ベクトルの要素の時差とはその位置と同じです。  
  
 挿入または要素を消去するには、反復子によって指定された値を変更することも、指定された位置に格納されている要素の値を変更できます。 (コンテナーは、要素にコピーまたは下矢印を挿入する前に穴を作成するか、消去後に穴を入力する必要があります)。いずれにしても、ベクターの反復子は有効ですが、範囲内にそのバイアス限り`[0, size()]`です。 さらに、有効な反復子は dereferencable--これを使用して、アクセスまたはそのバイアスと等しくない場合に限り指定--要素の値を変更することができます`size()`です。  
  
 消去、または要素を削除する、格納されている値のデストラクターを呼び出します。 コンテナーを破棄するには、すべての要素が消去されます。 したがって、要素型が ref クラスは、コンテナーを実現する要素よりも長くありませんコンテナー ただし、ハンドルのコンテナーには、その要素は破棄されません。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/vector >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [一覧 (STL/CLR)](../dotnet/list-stl-clr.md)   
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [キュー (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [スタック (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [vector::size (STL/CLR)](../dotnet/vector-size-stl-clr.md)  
 [STL/CLR ライブラリ リファレンス](../dotnet/stl-clr-library-reference.md)