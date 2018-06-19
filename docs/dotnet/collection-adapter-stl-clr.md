---
title: collection_adapter (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::collection_adapter
dev_langs:
- C++
helpviewer_keywords:
- collection_adapter class [STL/CLR]
ms.assetid: 31964058-1f50-48bf-82c2-b0b3cc8a7887
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 62fb5dc48175d755771960e9121c3371a0292595
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33114446"
---
# <a name="collectionadapter-stlclr"></a>collection_adapter (STL/CLR)
STL/CLR コンテナーとして使用するための .NET コレクションをラップします。 A`collection_adapter`単純 STL/CLR コンテナー オブジェクトを表すテンプレート クラスです。 メソッドは、基本クラス ライブラリ (BCL) インターフェイスをラップし、被制御シーケンスの操作に使用する反復子のペアを返します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Coll>  
    ref class collection_adapter;  
  
template<>  
    ref class collection_adapter<  
        System::Collections::ICollection>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IEnumerable>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IList>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IDictionary>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::ICollection<Value>>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IEnumerable<Value>>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IList<Value>>;  
template<typename Key,  
    typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IDictionary<Key, Value>>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 Coll  
 ラップされたコレクションの型。  
  
## <a name="specializations"></a>特殊化  
  
|特殊化|説明|  
|--------------------|-----------------|  
|IEnumerable|要素間のシーケンス。|  
|ICollection|要素のグループを保持します。|  
|IList|要素の順序付きのグループを保持します。|  
|IDictionary|{キー、値} のセットの管理のペア。|  
|IEnumerable\<値 >|型指定された要素をシーケンス。|  
|ICollection\<値 >|型指定された要素のグループを保持します。|  
|IList\<値 >|型指定された要素の順序付きのグループを保持します。|  
|IDictionary\<値 >|型指定された {キー、値} のセットを維持のペア。|  
  
## <a name="members"></a>メンバー  
  
|型定義|説明|  
|---------------------|-----------------|  
|[collection_adapter::difference_type (STL/CLR)](../dotnet/collection-adapter-difference-type-stl-clr.md)|2 つの要素間の距離を表す、符号付きの型です。|  
|[collection_adapter::iterator (STL/CLR)](../dotnet/collection-adapter-iterator-stl-clr.md)|被制御シーケンスの反復子の型です。|  
|[collection_adapter::key_type (STL/CLR)](../dotnet/collection-adapter-key-type-stl-clr.md)|ディクショナリのキーの型。|  
|[collection_adapter::mapped_type (STL/CLR)](../dotnet/collection-adapter-mapped-type-stl-clr.md)|ディクショナリの値の型。|  
|[collection_adapter::reference (STL/CLR)](../dotnet/collection-adapter-reference-stl-clr.md)|要素への参照の型です。|  
|[collection_adapter::size_type (STL/CLR)](../dotnet/collection-adapter-size-type-stl-clr.md)|2 つの要素間の距離を表す、符号付きの型です。|  
|[collection_adapter::value_type (STL/CLR)](../dotnet/collection-adapter-value-type-stl-clr.md)|要素の型。|  
  
|メンバー関数|説明|  
|---------------------|-----------------|  
|[collection_adapter::base (STL/CLR)](../dotnet/collection-adapter-base-stl-clr.md)|ラップされた BCL インターフェイスを指定します。|  
|[collection_adapter::begin (STL/CLR)](../dotnet/collection-adapter-begin-stl-clr.md)|被制御シーケンスの先頭を指定します。|  
|[collection_adapter::collection_adapter (STL/CLR)](../dotnet/collection-adapter-collection-adapter-stl-clr.md)|アダプター オブジェクトを構築します。|  
|[collection_adapter::end (STL/CLR)](../dotnet/collection-adapter-end-stl-clr.md)|被制御シーケンスの末尾を指定します。|  
|[collection_adapter::size (STL/CLR)](../dotnet/collection-adapter-size-stl-clr.md)|要素の数をカウントします。|  
|[collection_adapter::swap (STL/CLR)](../dotnet/collection-adapter-swap-stl-clr.md)|2 つのコンテナーのコンテンツを交換します。|  
  
|演算子|説明|  
|--------------|-----------------|  
|[collection_adapter::operator= (STL/CLR)](../dotnet/collection-adapter-operator-assign-stl-clr.md)|格納された BCL ハンドルを置換します。|  
  
## <a name="remarks"></a>コメント  
 STL/CLR コンテナーとして BCL コンテナーを操作するのにには、このテンプレート クラスを使用します。 `collection_adapter`要素のシーケンスを制御 BCL インターフェイスへのハンドルを格納します。 A`collection_adapter`オブジェクト`X`入力反復子のペアを返します`X.begin()`と`X.end()`の順序で、要素のアクセスに使用することです。 特化された型の一部も記述できます`X.size()`被制御シーケンスの長さを決定します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext アダプター/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)   
 [make_collection (STL/CLR)](../dotnet/make-collection-stl-clr.md)