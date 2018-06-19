---
title: 設定 (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::set
dev_langs:
- C++
helpviewer_keywords:
- <cliext/set> header [STL/CLR]
- <set> header [STL/CLR]
- set class [STL/CLR]
ms.assetid: 27d3628c-741a-43a7-bef1-5085536f679e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d6a7ebf4d15d85cb43a6f7101c70e444067a3f7b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33172804"
---
# <a name="set-stlclr"></a>set (STL/CLR)
このテンプレート クラスでは、双方向のアクセス権を持つ要素の可変長シーケンスを制御するオブジェクトについて説明します。 コンテナーを使用する`set`1 つの要素を格納する各ノードのバランスの取れた (ほとんど) の順序付けられたツリーとして要素のシーケンスを管理します。  
  
 下記に、`GValue`と同じ`GKey`、さらには同じ`Key`ref 型を後者には、しない限り、どのケースでは`Key^`です。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Key>  
    ref class set  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::ITree<Gkey, GValue>  
    { ..... };  
```  
  
#### <a name="parameters"></a>パラメーター  
 キー  
 被制御シーケンス内の要素の主要な構成要素の型。  
  
## <a name="members"></a>メンバー  
  
|型定義|説明|  
|---------------------|-----------------|  
|[set::const_iterator (STL/CLR)](../dotnet/set-const-iterator-stl-clr.md)|被制御シーケンスの定数反復子の型です。|  
|[set::const_reference (STL/CLR)](../dotnet/set-const-reference-stl-clr.md)|要素への定数参照の型です。|  
|[set::const_reverse_iterator (STL/CLR)](../dotnet/set-const-reverse-iterator-stl-clr.md)|被制御シーケンスの定数反転反復子の型です。|  
|[set::difference_type (STL/CLR)](../dotnet/set-difference-type-stl-clr.md)|2 つの要素間の距離を (場合によっては符号付き) の型。|  
|[set::generic_container (STL/CLR)](../dotnet/set-generic-container-stl-clr.md)|コンテナーのジェネリック インターフェイスの型。|  
|[set::generic_iterator (STL/CLR)](../dotnet/set-generic-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反復子の型。|  
|[set::generic_reverse_iterator (STL/CLR)](../dotnet/set-generic-reverse-iterator-stl-clr.md)|コンテナーのジェネリック インターフェイスの反転反復子の型。|  
|[set::generic_value (STL/CLR)](../dotnet/set-generic-value-stl-clr.md)|コンテナーのジェネリック インターフェイスの要素の型。|  
|[set::iterator (STL/CLR)](../dotnet/set-iterator-stl-clr.md)|被制御シーケンスの反復子の型です。|  
|[set::key_compare (STL/CLR)](../dotnet/set-key-compare-stl-clr.md)|2 つのキーの順序付けのデリゲート。|  
|[set::key_type (STL/CLR)](../dotnet/set-key-type-stl-clr.md)|順序付けキーの型です。|  
|[set::reference (STL/CLR)](../dotnet/set-reference-stl-clr.md)|要素への参照の型です。|  
|[set::reverse_iterator (STL/CLR)](../dotnet/set-reverse-iterator-stl-clr.md)|被制御シーケンスの反転反復子の型です。|  
|[set::size_type (STL/CLR)](../dotnet/set-size-type-stl-clr.md)|(負符号) 距離は 2 つの要素の型。|  
|[set::value_compare (STL/CLR)](../dotnet/set-value-compare-stl-clr.md)|2 つの要素値の順序付けのデリゲート。|  
|[set::value_type (STL/CLR)](../dotnet/set-value-type-stl-clr.md)|要素の型。|  
  
|メンバー関数|説明|  
|---------------------|-----------------|  
|[set::begin (STL/CLR)](../dotnet/set-begin-stl-clr.md)|被制御シーケンスの先頭を指定します。|  
|[set::clear (STL/CLR)](../dotnet/set-clear-stl-clr.md)|すべての要素を削除します。|  
|[set::count (STL/CLR)](../dotnet/set-count-stl-clr.md)|指定したキーに一致する要素の数をカウントします。|  
|[set::empty (STL/CLR)](../dotnet/set-empty-stl-clr.md)|要素が存在しないかどうかをテストします。|  
|[set::end (STL/CLR)](../dotnet/set-end-stl-clr.md)|被制御シーケンスの末尾を指定します。|  
|[set::equal_range (STL/CLR)](../dotnet/set-equal-range-stl-clr.md)|指定したキーに一致する範囲を検索します。|  
|[set::erase (STL/CLR)](../dotnet/set-erase-stl-clr.md)|指定した位置にある要素を削除します。|  
|[set::find (STL/CLR)](../dotnet/set-find-stl-clr.md)|指定したキーに一致する要素を検索します。|  
|[set::insert (STL/CLR)](../dotnet/set-insert-stl-clr.md)|要素を追加します。|  
|[set::key_comp (STL/CLR)](../dotnet/set-key-comp-stl-clr.md)|2 つのキーの順序付けのデリゲートをコピーします。|  
|[set::lower_bound (STL/CLR)](../dotnet/set-lower-bound-stl-clr.md)|指定したキーに一致する範囲の先頭を検出します。|  
|[set::make_value (STL/CLR)](../dotnet/set-make-value-stl-clr.md)|値オブジェクトを構築します。|  
|[set::rbegin (STL/CLR)](../dotnet/set-rbegin-stl-clr.md)|反転被制御シーケンスの先頭を指定します。|  
|[set::rend (STL/CLR)](../dotnet/set-rend-stl-clr.md)|反転被制御シーケンスの末尾を指定します。|  
|[set::set (STL/CLR)](../dotnet/set-set-stl-clr.md)|コンテナー オブジェクトを構築します。|  
|[set::size (STL/CLR)](../dotnet/set-size-stl-clr.md)|要素の数をカウントします。|  
|[set::swap (STL/CLR)](../dotnet/set-swap-stl-clr.md)|2 つのコンテナーのコンテンツを交換します。|  
|[set::to_array (STL/CLR)](../dotnet/set-to-array-stl-clr.md)|被制御シーケンスを新しい配列にコピーします。|  
|[set::upper_bound (STL/CLR)](../dotnet/set-upper-bound-stl-clr.md)|指定したキーに一致する範囲の末尾を検索します。|  
|[set::value_comp (STL/CLR)](../dotnet/set-value-comp-stl-clr.md)|2 つの要素値の順序付けのデリゲートをコピーします。|  
  
|演算子|説明|  
|--------------|-----------------|  
|[set::operator= (STL/CLR)](../dotnet/set-operator-assign-stl-clr.md)|被制御シーケンスを置き換えます。|  
|[operator!= (set) (STL/CLR)](../dotnet/operator-inequality-set-stl-clr.md)|かどうかを`set`オブジェクトが他と等しくない`set`オブジェクト。|  
|[operator< (set) (STL/CLR)](../dotnet/operator-less-than-set-stl-clr.md)|かどうかを`set`オブジェクトが他よりも小さい`set`オブジェクト。|  
|[operator<= (set) (STL/CLR)](../dotnet/operator-less-or-equal-set-stl-clr.md)|かどうかを`set`オブジェクトが別に小さい`set`オブジェクト。|  
|[operator== (set) (STL/CLR)](../dotnet/operator-equality-set-stl-clr.md)|かどうかを`set`オブジェクトが他と等しい`set`オブジェクト。|  
|[operator> (set) (STL/CLR)](../dotnet/operator-greater-than-set-stl-clr.md)|かどうかを`set`オブジェクトが他よりも大きい`set`オブジェクト。|  
|[operator>= (set) (STL/CLR)](../dotnet/operator-greater-or-equal-set-stl-clr.md)|かどうかを`set`オブジェクトがより大きいか等しい間`set`オブジェクト。|  
  
## <a name="interfaces"></a>インターフェイス  
  
|Interface|説明|  
|---------------|-----------------|  
|<xref:System.ICloneable>|オブジェクトが重複してください。|  
|<xref:System.Collections.IEnumerable>|要素を順番にします。|  
|<xref:System.Collections.ICollection>|要素のグループを管理します。|  
|<xref:System.Collections.Generic.IEnumerable%601>|型指定された要素を順番にします。|  
|<xref:System.Collections.Generic.ICollection%601>|型指定された要素のグループを管理します。|  
|ITree\<キー、値 >|ジェネリックなコンテナーを管理します。|  
  
## <a name="remarks"></a>コメント  
 オブジェクトは、割り当てし、個々 のノードとして、制御するシーケンスの記憶域を解放します。 順序付けられた 1 つのノードの内容を別にコピーからではなく、ノード間のリンクを変更することにより保持される (ほとんど) バランスの良いツリーに要素を挿入します。 つまり、挿入し、残りの要素を中断することがなく自由に要素を削除することができます。  
  
 オブジェクトがストアド デリゲート型のオブジェクトを呼び出すことによって、制御するシーケンスを並べ替えます[set::key_compare (STL/CLR)](../dotnet/set-key-compare-stl-clr.md)です。 セットを構築するときにストアド デリゲート オブジェクトを指定することができます。デリゲート オブジェクトを指定しないと、既定値が比較`operator<(key_type, key_type)`です。 このメンバー関数を呼び出すことによってこのストアド オブジェクトにアクセスする[set::key_comp (STL/CLR)](../dotnet/set-key-comp-stl-clr.md)`()`です。  
  
 このようなデリゲート オブジェクト必要があります、厳密弱順序強制型のキーで[set::key_type (STL/CLR)](../dotnet/set-key-type-stl-clr.md)です。 つまり、任意の 2 つのキーの`X`と`Y`:  
  
 `key_comp()(X, Y)` すべての呼び出しでブール値を同じ結果を返します。  
  
 場合`key_comp()(X, Y)`が true の場合、 `key_comp()(Y, X)` false である必要があります。  
  
 場合`key_comp()(X, Y)`が true の場合、`X`をする前に並べ替えるといいます`Y`です。  
  
 場合`!key_comp()(X, Y) && !key_comp()(Y, X)`が true の場合、`X`と`Y`大小関係が等しいと呼ばれます。  
  
 任意の要素に対して`X`の直前まで`Y`、被制御シーケンスの`key_comp()(Y, X)`は false。 (既定のデリゲート オブジェクトのキーしない値が減少します。)テンプレート クラスとは異なり[設定](../dotnet/set-stl-clr.md)、テンプレート クラスのオブジェクト`set`すべての要素のキーが一意であることは不要です。 (2 つまたは複数のキーが持てると同じ順序です。)  
  
 各要素は、欄と値の両方として機能します。 シーケンスは、シーケンス (対数時間) の検索、挿入、削除、任意の要素数の要素の数の対数に比例して操作できるような方法で表されます。 要素を挿入しても反復子の有効性は失われません。また、要素を削除した場合は、削除された要素を指す反復子だけが無効化されます。  
  
 セットは、ステップ隣接する要素を被制御シーケンス内の要素を指定する反復子を指定することができますが、双方向反復子をサポートします。 特殊なヘッド ノードによって返される反復子に対応[set::end (STL/CLR)](../dotnet/set-end-stl-clr.md)`()`です。 存在する場合、被制御シーケンスの最後の要素に到達するこの反復子をデクリメントすることができます。 ヘッド ノードに到達するセットの反復子をインクリメントすることができは、比較に等しい`end()`です。 によって返される反復子を逆参照することはできませんが、`end()`です。  
  
 ランダム アクセス反復子が必要です--数値の位置を直接指定されたセットの要素を参照することはできないことに注意してください。  
  
 セットの反復子は、その関連付けセットのノードに関連付けられているコンテナーへのハンドルを格納するへのハンドルを格納します。 反復子は、それらの関連するコンテナー オブジェクトにのみ使用できます。 セットの反復子は、その関連付けセットのノードにいくつかのセットに関連付けられている限り有効です。 さらに、有効な反復子が dereferencable--と等しくない場合に限り指定--要素の値を変更またはアクセスを行うこともできます`end()`です。  
  
 消去、または要素を削除する、格納されている値のデストラクターを呼び出します。 コンテナーを破棄するには、すべての要素が消去されます。 したがって、要素型が ref クラスは、コンテナーを実現する要素よりも長くありませんコンテナー ただし、ハンドルのコンテナーは`not`その要素を破棄します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext と set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [マップ (STL/CLR)](../dotnet/map-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [STL/CLR ライブラリ リファレンス](../dotnet/stl-clr-library-reference.md)