---
title: 一覧 (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list
dev_langs:
- C++
helpviewer_keywords:
- <cliext/list> header [STL/CLR]
- list class [STL/CLR]
- <list> header [STL/CLR]
ms.assetid: a70c45c8-a257-4f6b-8434-b27ff6685bac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4ff009da3ca29697e9b3affceb424bcd84b9b896
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33141751"
---
# <a name="list-stlclr"></a>list (STL/CLR)
このテンプレート クラスでは、双方向のアクセス権を持つ要素の可変長シーケンスを制御するオブジェクトについて説明します。 コンテナーを使用する`list`1 つの要素を格納する各ノードの双方向リンク リストとして要素のシーケンスを管理します。  
  
 下記に、`GValue`と同じ`Value`ref 型を後者には、しない限り、どのケースでは`Value^`します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Value>  
    ref class list  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        Microsoft::VisualC::StlClr::IList<GValue>  
    { ..... };  
```  
  
#### <a name="parameters"></a>パラメーター  
 [値]  
 被制御シーケンス内の要素の型。  
  
## <a name="members"></a>メンバー  
  
|型定義|説明|  
|---------------------|-----------------|  
|[list::const_iterator (STL/CLR)](../dotnet/list-const-iterator-stl-clr.md)|被制御シーケンスの定数反復子の型です。|  
|[list::const_reference (STL/CLR)](../dotnet/list-const-reference-stl-clr.md)|要素への定数参照の型です。|  
|[list::const_reverse_iterator (STL/CLR)](../dotnet/list-const-reverse-iterator-stl-clr.md)|被制御シーケンスの定数反転反復子の型です。|  
|[list::difference_type (STL/CLR)](../dotnet/list-difference-type-stl-clr.md)|2 つの要素間の距離を表す、符号付きの型です。|  
|[list::generic_container (STL/CLR)](../dotnet/list-generic-container-stl-clr.md)|コンテナーのジェネリック インターフェイスの型。|  
|[list::generic_iterator (STL/CLR)](../dotnet/list-generic-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反復子の型。|  
|[list::generic_reverse_iterator (STL/CLR)](../dotnet/list-generic-reverse-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反転反復子の型。|  
|[list::generic_value (STL/CLR)](../dotnet/list-generic-value-stl-clr.md)|コンテナーのジェネリック インターフェイスの要素の型。|  
|[list::iterator (STL/CLR)](../dotnet/list-iterator-stl-clr.md)|被制御シーケンスの反復子の型です。|  
|[list::reference (STL/CLR)](../dotnet/list-reference-stl-clr.md)|要素への参照の型です。|  
|[list::reverse_iterator (STL/CLR)](../dotnet/list-reverse-iterator-stl-clr.md)|被制御シーケンスの反転反復子の型です。|  
|[list::size_type (STL/CLR)](../dotnet/list-size-type-stl-clr.md)|2 つの要素間の距離を表す、符号付きの型です。|  
|[list::value_type (STL/CLR)](../dotnet/list-value-type-stl-clr.md)|要素の型。|  
  
|メンバー関数|説明|  
|---------------------|-----------------|  
|[list::assign (STL/CLR)](../dotnet/list-assign-stl-clr.md)|すべての要素を置換します。|  
|[list::back (STL/CLR)](../dotnet/list-back-stl-clr.md)|最後の要素にアクセスします。|  
|[list::begin (STL/CLR)](../dotnet/list-begin-stl-clr.md)|被制御シーケンスの先頭を指定します。|  
|[list::clear (STL/CLR)](../dotnet/list-clear-stl-clr.md)|すべての要素を削除します。|  
|[list::empty (STL/CLR)](../dotnet/list-empty-stl-clr.md)|要素が存在しないかどうかをテストします。|  
|[list::end (STL/CLR)](../dotnet/list-end-stl-clr.md)|被制御シーケンスの末尾を指定します。|  
|[list::erase (STL/CLR)](../dotnet/list-erase-stl-clr.md)|指定した位置にある要素を削除します。|  
|[list::front (STL/CLR)](../dotnet/list-front-stl-clr.md)|最初の要素にアクセスします。|  
|[list::insert (STL/CLR)](../dotnet/list-insert-stl-clr.md)|指定した位置にある要素を追加します。|  
|[list::list (STL/CLR)](../dotnet/list-list-stl-clr.md)|コンテナー オブジェクトを構築します。|  
|[list::merge (STL/CLR)](../dotnet/list-merge-stl-clr.md)|2 つの被制御シーケンスの順序をマージします。|  
|[list::pop_back (STL/CLR)](../dotnet/list-pop-back-stl-clr.md)|最後の要素を削除します。|  
|[list::pop_front (STL/CLR)](../dotnet/list-pop-front-stl-clr.md)|最初の要素を削除します。|  
|[list::push_back (STL/CLR)](../dotnet/list-push-back-stl-clr.md)|新しい最後の要素を追加します。|  
|[list::push_front (STL/CLR)](../dotnet/list-push-front-stl-clr.md)|新しい最初の要素を追加します。|  
|[list::rbegin (STL/CLR)](../dotnet/list-rbegin-stl-clr.md)|反転被制御シーケンスの先頭を指定します。|  
|[list::remove (STL/CLR)](../dotnet/list-remove-stl-clr.md)|指定した値を持つ要素を削除します。|  
|[list::remove_if (STL/CLR)](../dotnet/list-remove-if-stl-clr.md)|指定されたテストに合格した要素を削除します。|  
|[list::rend (STL/CLR)](../dotnet/list-rend-stl-clr.md)|反転被制御シーケンスの末尾を指定します。|  
|[list::resize (STL/CLR)](../dotnet/list-resize-stl-clr.md)|要素の数を変更します。|  
|[list::reverse (STL/CLR)](../dotnet/list-reverse-stl-clr.md)|被制御シーケンスを反転させます。|  
|[list::size (STL/CLR)](../dotnet/list-size-stl-clr.md)|要素の数をカウントします。|  
|[list::sort (STL/CLR)](../dotnet/list-sort-stl-clr.md)|被制御シーケンスを並べ替えます。|  
|[list::splice (STL/CLR)](../dotnet/list-splice-stl-clr.md)|ノード間のリンクを再接合します。|  
|[list::swap (STL/CLR)](../dotnet/list-swap-stl-clr.md)|2 つのコンテナーのコンテンツを交換します。|  
|[list::to_array (STL/CLR)](../dotnet/list-to-array-stl-clr.md)|被制御シーケンスを新しい配列にコピーします。|  
|[list::unique (STL/CLR)](../dotnet/list-unique-stl-clr.md)|指定されたテストに合格した隣接する要素を削除します。|  
  
|プロパティ|説明|  
|--------------|-----------------|  
|[list::back_item (STL/CLR)](../dotnet/list-back-item-stl-clr.md)|最後の要素にアクセスします。|  
|[list::front_item (STL/CLR)](../dotnet/list-front-item-stl-clr.md)|最初の要素にアクセスします。|  
  
|演算子|説明|  
|--------------|-----------------|  
|[list::operator= (STL/CLR)](../dotnet/list-operator-assign-stl-clr.md)|被制御シーケンスを置き換えます。|  
|[operator!= (list) (STL/CLR)](../dotnet/operator-inequality-list-stl-clr.md)|かどうかを`list`オブジェクトが他と等しくない`list`オブジェクト。|  
|[operator< (list) (STL/CLR)](../dotnet/operator-less-than-list-stl-clr.md)|かどうかを`list`オブジェクトが他よりも小さい`list`オブジェクト。|  
|[operator<= (list) (STL/CLR)](../dotnet/operator-less-or-equal-list-stl-clr.md)|かどうかを`list`オブジェクトが別に小さい`list`オブジェクト。|  
|[operator== (list) (STL/CLR)](../dotnet/operator-equality-list-stl-clr.md)|かどうかを`list`オブジェクトが他と等しい`list`オブジェクト。|  
|[operator> (list) (STL/CLR)](../dotnet/operator-greater-than-list-stl-clr.md)|かどうかを`list`オブジェクトが他よりも大きい`list`オブジェクト。|  
|[operator>= (list) (STL/CLR)](../dotnet/operator-greater-or-equal-list-stl-clr.md)|かどうかを`list`オブジェクトがより大きいか等しい間`list`オブジェクト。|  
  
## <a name="interfaces"></a>インターフェイス  
  
|Interface|説明|  
|---------------|-----------------|  
|<xref:System.ICloneable>|オブジェクトが重複してください。|  
|<xref:System.Collections.IEnumerable>|要素を順番にします。|  
|<xref:System.Collections.ICollection>|要素のグループを管理します。|  
|<xref:System.Collections.Generic.IEnumerable%601>|型指定された要素を順番にします。|  
|<xref:System.Collections.Generic.ICollection%601>|型指定された要素のグループを管理します。|  
|IList\<値 >|ジェネリックなコンテナーを管理します。|  
  
## <a name="remarks"></a>コメント  
 オブジェクトは、割り当てし、双方向リンク リスト内の個々 のノードとして、制御するシーケンスの記憶域を解放します。 別の 1 つのノードの内容のコピーからではなく、ノード間のリンクを変更して要素を並べ替えます。 つまり、挿入し、残りの要素を中断することがなく自由に要素を削除することができます。 したがって、一覧には、基になるコンテナー テンプレート クラスには適して[キュー (STL/CLR)](../dotnet/queue-stl-clr.md)またはテンプレート クラス[スタック (STL/CLR)](../dotnet/stack-stl-clr.md)です。  
  
 A`list`オブジェクトがサポートする双方向反復子は、被制御シーケンス内の要素を指定する反復子を指定する、隣接する要素をステップ実行できます。 特殊なヘッド ノードによって返される反復子に対応[list::end (STL/CLR)](../dotnet/list-end-stl-clr.md)`()`です。 存在する場合、被制御シーケンスの最後の要素に到達するこの反復子をデクリメントすることができます。 ヘッド ノードに到達するリストの反復子をインクリメントすることができは、比較に等しい`end()`です。 によって返される反復子を逆参照することはできませんが、`end()`です。  
  
 ランダム アクセス反復子が必要です--数値の位置を直接指定されたリストの要素を参照することはできないことに注意してください。 一覧は`not`テンプレート クラスの基になるコンテナーとして使用可能な[priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)です。  
  
 リストの反復子は、それに関連付けられているコンテナーへのハンドルを格納する関連付けられたリスト ノードへのハンドルを格納します。 反復子は、それらの関連するコンテナー オブジェクトにのみ使用できます。 リストの反復子は、関連付けられているリスト ノードのいくつかのリストに関連付けられている限り有効です。 さらに、有効な反復子が dereferencable--と等しくない場合に限り指定--要素の値を変更またはアクセスを行うこともできます`end()`です。  
  
 消去、または要素を削除する、格納されている値のデストラクターを呼び出します。 コンテナーを破棄するには、すべての要素が消去されます。 したがって、要素型が ref クラスは、コンテナーを実現する要素よりも長くありませんコンテナー ただし、ハンドルのコンテナーは`not`その要素を破棄します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/一覧 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [キュー (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [スタック (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [ベクトル (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [STL/CLR ライブラリ リファレンス](../dotnet/stl-clr-library-reference.md)