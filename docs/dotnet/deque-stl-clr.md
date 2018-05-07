---
title: deque (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque
dev_langs:
- C++
helpviewer_keywords:
- deque class [STL/CLR]
- <deque> header [STL/CLR]
- <cliext/deque> header [STL/CLR]
ms.assetid: dd669da3-3c0e-45e9-8596-f6b483720941
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 11436466dadf4b06e604af6e2b5150a22c4ed241
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="deque-stlclr"></a>deque (STL/CLR)
このテンプレート クラスでは、ランダム アクセス権を持つ要素の可変長シーケンスを制御するオブジェクトについて説明します。 コンテナーを使用する`deque`ストレージの連続したブロックのようですが、拡大したり、一方の端を残りの要素をコピーする必要がない縮小することができますの要素のシーケンスを管理します。 効率的に、実装できるため、`double-ended queue`です。 (したがって名前です)。  
  
 下記に、`GValue`と同じ`Value`ref 型を後者には、しない限り、どのケースでは`Value^`します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Value>  
    ref class deque  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IDeque<GValue>  
    { ..... };  
```  
  
#### <a name="parameters"></a>パラメーター  
 GValue  
 被制御シーケンス内の要素のジェネリック型。  
  
 [値]  
 被制御シーケンス内の要素の型。  
  
## <a name="members"></a>メンバー  
  
|型定義|説明|  
|---------------------|-----------------|  
|[deque::const_iterator (STL/CLR)](../dotnet/deque-const-iterator-stl-clr.md)|被制御シーケンスの定数反復子の型です。|  
|[deque::const_reference (STL/CLR)](../dotnet/deque-const-reference-stl-clr.md)|要素への定数参照の型です。|  
|[deque::const_reverse_iterator (STL/CLR)](../dotnet/deque-const-reverse-iterator-stl-clr.md)|被制御シーケンスの定数反転反復子の型です。|  
|[deque::difference_type (STL/CLR)](../dotnet/deque-difference-type-stl-clr.md)|2 つの要素間の距離を表す、符号付きの型です。|  
|[deque::generic_container (STL/CLR)](../dotnet/deque-generic-container-stl-clr.md)|コンテナーのジェネリック インターフェイスの型。|  
|[deque::generic_iterator (STL/CLR)](../dotnet/deque-generic-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反復子の型。|  
|[deque::generic_reverse_iterator (STL/CLR)](../dotnet/deque-generic-reverse-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反転反復子の型。|  
|[deque::generic_value (STL/CLR)](../dotnet/deque-generic-value-stl-clr.md)|コンテナーのジェネリック インターフェイスの要素の型。|  
|[deque::iterator (STL/CLR)](../dotnet/deque-iterator-stl-clr.md)|被制御シーケンスの反復子の型です。|  
|[deque::reference (STL/CLR)](../dotnet/deque-reference-stl-clr.md)|要素への参照の型です。|  
|[deque::reverse_iterator (STL/CLR)](../dotnet/deque-reverse-iterator-stl-clr.md)|被制御シーケンスの反転反復子の型です。|  
|[deque::size_type (STL/CLR)](../dotnet/deque-size-type-stl-clr.md)|2 つの要素間の距離を表す、符号付きの型です。|  
|[deque::value_type (STL/CLR)](../dotnet/deque-value-type-stl-clr.md)|要素の型。|  
  
|メンバー関数|説明|  
|---------------------|-----------------|  
|[deque::assign (STL/CLR)](../dotnet/deque-assign-stl-clr.md)|すべての要素を置換します。|  
|[deque::at (STL/CLR)](../dotnet/deque-at-stl-clr.md)|指定した位置にある要素にアクセスします。|  
|[deque::back (STL/CLR)](../dotnet/deque-back-stl-clr.md)|最後の要素にアクセスします。|  
|[deque::begin (STL/CLR)](../dotnet/deque-begin-stl-clr.md)|被制御シーケンスの先頭を指定します。|  
|[deque::clear (STL/CLR)](../dotnet/deque-clear-stl-clr.md)|すべての要素を削除します。|  
|[deque::deque (STL/CLR)](../dotnet/deque-deque-stl-clr.md)|コンテナー オブジェクトを構築します。|  
|[deque::empty (STL/CLR)](../dotnet/deque-empty-stl-clr.md)|要素が存在しないかどうかをテストします。|  
|[deque::end (STL/CLR)](../dotnet/deque-end-stl-clr.md)|被制御シーケンスの末尾を指定します。|  
|[deque::erase (STL/CLR)](../dotnet/deque-erase-stl-clr.md)|指定した位置にある要素を削除します。|  
|[deque::front (STL/CLR)](../dotnet/deque-front-stl-clr.md)|最初の要素にアクセスします。|  
|[deque::insert (STL/CLR)](../dotnet/deque-insert-stl-clr.md)|指定した位置にある要素を追加します。|  
|[deque::pop_back (STL/CLR)](../dotnet/deque-pop-back-stl-clr.md)|最後の要素を削除します。|  
|[deque::pop_front (STL/CLR)](../dotnet/deque-pop-front-stl-clr.md)|最初の要素を削除します。|  
|[deque::push_back (STL/CLR)](../dotnet/deque-push-back-stl-clr.md)|新しい最後の要素を追加します。|  
|[deque::push_front (STL/CLR)](../dotnet/deque-push-front-stl-clr.md)|新しい最初の要素を追加します。|  
|[deque::rbegin (STL/CLR)](../dotnet/deque-rbegin-stl-clr.md)|反転被制御シーケンスの先頭を指定します。|  
|[deque::rend (STL/CLR)](../dotnet/deque-rend-stl-clr.md)|反転被制御シーケンスの末尾を指定します。|  
|[deque::resize (STL/CLR)](../dotnet/deque-resize-stl-clr.md)|要素の数を変更します。|  
|[deque::size (STL/CLR)](../dotnet/deque-size-stl-clr.md)|要素の数をカウントします。|  
|[deque::swap (STL/CLR)](../dotnet/deque-swap-stl-clr.md)|2 つのコンテナーのコンテンツを交換します。|  
|[deque::to_array (STL/CLR)](../dotnet/deque-to-array-stl-clr.md)|被制御シーケンスを新しい配列にコピーします。|  
  
|プロパティ|説明|  
|--------------|-----------------|  
|[deque::back_item (STL/CLR)](../dotnet/deque-back-item-stl-clr.md)|最後の要素にアクセスします。|  
|[deque::front_item (STL/CLR)](../dotnet/deque-front-item-stl-clr.md)|最初の要素にアクセスします。|  
  
|演算子|説明|  
|--------------|-----------------|  
|[deque::operator!= (STL/CLR)](../dotnet/deque-operator-inequality-stl-clr.md)|2 つの場合を決定`deque`オブジェクトが等しくないです。|  
|[deque::operator(STL/CLR)](../dotnet/deque-operator-stl-clr.md)|指定した位置にある要素にアクセスします。|  
|[operator< (deque) (STL/CLR)](../dotnet/operator-less-than-deque-stl-clr.md)|かどうかを`deque`オブジェクトが他よりも小さい`deque`オブジェクト。|  
|[operator<= (deque) (STL/CLR)](../dotnet/operator-less-or-equal-deque-stl-clr.md)|かどうかを`deque`オブジェクトが別に小さい`deque`オブジェクト。|  
|[operator= (deque) (STL/CLR)](../dotnet/operator-assign-deque-stl-clr.md)|被制御シーケンスを置き換えます。|  
|[operator== (deque) (STL/CLR)](../dotnet/operator-equality-deque-stl-clr.md)|かどうかを`deque`オブジェクトが他と等しい`deque`オブジェクト。|  
|[operator> (deque) (STL/CLR)](../dotnet/operator-greater-than-deque-stl-clr.md)|かどうかを`deque`オブジェクトが他よりも大きい`deque`オブジェクト。|  
|[operator>= (deque) (STL/CLR)](../dotnet/operator-greater-or-equal-deque-stl-clr.md)|かどうかを`deque`オブジェクトがより大きいか等しい間`deque`オブジェクト。|  
  
## <a name="interfaces"></a>インターフェイス  
  
|Interface|説明|  
|---------------|-----------------|  
|<xref:System.ICloneable>|オブジェクトが重複してください。|  
|<xref:System.Collections.IEnumerable>|要素を順番にします。|  
|<xref:System.Collections.ICollection>|要素のグループを管理します。|  
|<xref:System.Collections.Generic.IEnumerable%601>|型指定された要素を順番にします。|  
|<xref:System.Collections.Generic.ICollection%601>|型指定された要素のグループを管理します。|  
|<xref:System.Collections.Generic.IList%601>|型指定された要素の順序付きのグループを管理します。|  
|IDeque < 値\>|ジェネリックなコンテナーを管理します。|  
  
## <a name="remarks"></a>コメント  
 オブジェクトは、割り当てし、ストアドのブロックを指定したハンドルの配列を制御するシーケンスの記憶域を解放`Value`要素。 配列は、要求時に拡張します。 拡張は、付加することか、新しい要素を追加することのコストは一定の時間、残りの要素が分散されていない方法で発生します。 一定の時間内と残りの要素を中断することがなく先頭または末尾にある要素を削除することもできます。 したがって、deque です。 このテンプレート クラスを基になるコンテナーで有力候補[キュー (STL/CLR)](../dotnet/queue-stl-clr.md)またはテンプレート クラス[スタック (STL/CLR)](../dotnet/stack-stl-clr.md)です。  
  
 A`deque`オブジェクトは、するための最初の (フロント) 要素の 0 からカウントの位置を直接指定された要素を参照できますつまりランダム アクセス反復子をサポートしている[deque::size (STL/CLR)](../dotnet/deque-size-stl-clr.md) `() - 1`最後 (背面) の要素。 Deque が基になるコンテナー テンプレート クラスに適した候補であることも意味[priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)です。  
  
 Deque の反復子は、指定した要素のバイアスと共に、関連付けられている deque オブジェクトへのハンドルを格納します。 反復子は、それらの関連するコンテナー オブジェクトにのみ使用できます。 Deque の要素のバイアスは`not`の位置と同じとは限りません。 最初の要素が 0 のバイアス、次の追加要素バイアス 1 が次の先頭に追加された要素がバイアス-1 です。  
  
 挿入またはいずれかの端にある要素を消去するには`not`有効バイアスに格納されている要素の値を変更します。 挿入または消去内部要素、ただし、`can`反復子によって指定された値を変更することも、指定のバイアスに格納されている要素の値を変更します。 (コンテナーは、要素にコピーまたは下矢印を挿入する前に穴を作成するか、消去後に穴を入力する必要があります)。ただし、そのバイアスは、有効な要素を指定する限りは、deque 反復子は有効です。 さらに、有効な反復子は dereferencable--これを使用して、アクセスまたはそのバイアスがバイアスは、によって返される反復子と等しくない場合に限り指定--要素の値を変更することができます`end()`です。  
  
 消去、または要素を削除する、格納されている値のデストラクターを呼び出します。 コンテナーを破棄するには、すべての要素が消去されます。 したがって、要素型が ref クラスは、コンテナーを実現する要素よりも長くありませんコンテナー ただし、ハンドルのコンテナーは`not`その要素を破棄します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/deque >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [一覧 (STL/CLR)](../dotnet/list-stl-clr.md)   
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [キュー (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [スタック (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [ベクトル (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [STL/CLR ライブラリ リファレンス](../dotnet/stl-clr-library-reference.md)