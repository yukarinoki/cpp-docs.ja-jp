---
title: Platform::Collections::VectorView クラス |Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorView::VectorView
- COLLECTION/Platform::Collections::VectorView::First
- COLLECTION/Platform::Collections::VectorView::GetAt
- COLLECTION/Platform::Collections::VectorView::GetMany
- COLLECTION/Platform::Collections::VectorView::IndexOf
- COLLECTION/Platform::Collections::VectorView::Size
dev_langs:
- C++
helpviewer_keywords:
- VectorView Class
ms.assetid: 05cd461d-dce7-49d3-b0e7-2e5c78ed8192
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 598b5f6fcfefa03fe733ac7b6e5a8417278e6f01
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43690608"
---
# <a name="platformcollectionsvectorview-class"></a>Platform::Collections::VectorView クラス
インデックスによって個別にアクセスできるオブジェクトのシーケンシャル コレクションの読み取り専用ビューを表します。 コレクション内の各オブジェクトの型は、テンプレート パラメーターによって指定されます。  
  
## <a name="syntax"></a>構文  
  
```  
template <typename T, typename E>  
   ref class VectorView sealed;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 `VectorView` オブジェクトに格納されている要素の型。  
  
 `E`  
 `T`型の値との等値性をテストするための二項述語を指定します。 既定値は `std::equal_to<T>` です。  
  
### <a name="remarks"></a>Remarks  
 `VectorView`クラスが実装する、 [Windows::Foundation::Collections::IVectorView\<T >](/uwp/api/Windows.Foundation.Collections.IVectorView_T_)インターフェイス、および標準テンプレート ライブラリ反復子をサポートします。  
  
### <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[VectorView::VectorView](#ctor)|VectorView クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[VectorView::First](#first)|VectorView 内の最初の要素を指定する反復子を返します。|  
|[VectorView::GetAt](#getat)|指定されたインデックスで示される現在の VectorView の要素を取得します。|  
|[Vectorview::getmany](#getmany)|指定されたインデックスを開始位置として、現在の VectorView から項目のシーケンスを取得します。|  
|[VectorView::IndexOf](#indexof)|現在の VectorView 内で指定された項目を検索し、見つかった場合は項目のインデックスを返します。|  
|[VectorView::Size](#size)|現在の VectorView オブジェクトの要素数を返します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `VectorView`  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  

## <a name="first"></a>  Vectorview::first メソッド
VectorView 内の最初の要素を指定する反復子を返します。  
  
### <a name="syntax"></a>構文  
  
```  
  
virtual Windows::Foundation::Collections::IIterator<T>^   
   First();  
```  
  
### <a name="return-value"></a>戻り値  
 VectorView 内の最初の要素を指定する反復子。  
  
### <a name="remarks"></a>Remarks  
 First() によって返される反復子を保持する便利な方法で宣言された変数に戻り値を割り当てるには、**自動**推論キーワードを入力します。 たとえば、`auto x = myVectorView->First();` のようにします。  
  


## <a name="getat"></a>  Vectorview::getat メソッド
指定されたインデックスで示される現在の VectorView の要素を取得します。  
  
### <a name="syntax"></a>構文  
  
```  
  
T GetAt(  
   UInt32 index  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `index`  
 VectorView オブジェクト内の特定の要素を指定する、0 から始まる符号なし整数。  
  
### <a name="return-value"></a>戻り値  
 `index` パラメーターで指定された要素。 要素の型が、VectorView テンプレート パラメーターで指定された*T*します。  
  


## <a name="getmany"></a>  Vectorview::getmany メソッド
指定されたインデックスを開始位置として、現在の VectorView から項目のシーケンスを取得します。  
  
### <a name="syntax"></a>構文  
  
```  
  
virtual unsigned int GetMany(  
   unsigned int startIndex,   
   ::Platform::WriteOnlyArray<T>^ dest  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `startIndex`  
 取得する項目の 0 から始まるインデックス。  
  
 `dest`  
 ときにこの操作が完了したらで指定した要素から開始する項目の配列`startIndex`と VectorView 内の最後の要素で終了します。  
  
### <a name="return-value"></a>戻り値  
 取得した項目数。  
  


## <a name="indexof"></a>  Vectorview::indexof メソッド
現在の VectorView 内で指定された項目を検索し、見つかった場合は項目のインデックスを返します。  
  
### <a name="syntax"></a>構文  
  
```  
  
virtual bool IndexOf(  
   T value,  
   unsigned int* index  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `value`  
 検索する項目。  
  
 `index`  
 `value` パラメーターが見つかった場合は、項目の 0 から始まるインデックス。 それ以外の場合は 0。  
  
 `index` パラメーターは、項目が VectorView の最初の要素であるか、項目が見つからなかった場合は 0 です。 戻り値が `true` の場合、項目が見つかり、項目は最初の要素です。それ以外の場合は、項目は見つかっていません。  
  
### <a name="return-value"></a>戻り値  
 指定した項目が見つかった場合は `true`。それ以外の場合は `false`。  
  


## <a name="size"></a>  Vectorview::size メソッド
現在の VectorView オブジェクトの要素数を返します。  
  
### <a name="syntax"></a>構文  
  
```  
  
virtual property unsigned int Size;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の VectorView 内の要素数。  
  


## <a name="ctor"></a>  Vectorview::vectorview コンス トラクター
VectorView クラスの新しいインスタンスを初期化します。  
  
### <a name="syntax"></a>構文  
  
```  
VectorView();  
explicit VectorView(  
   UInt32 size  
);  
VectorView(  
   UInt32 size,  
   T value  
);  
explicit VectorView(  
   const ::std::vector<T>& v  
);  
explicit VectorView(  
   ::std::vector<T>&& v  
);  
VectorView(  
   const T * ptr,  
   UInt32 size  
);  
  
template <  
   size_t N  
>  
explicit VectorView(  
   const T (&arr)[N]  
);  
  
template <  
   size_t N  
>  
explicit VectorView(  
   const ::std::array<T,  
   N>& a  
);  
  
explicit VectorView(  
   const ::Platform::Array<T>^ arr  
);  
  
template <  
   typename InIt  
>  
VectorView(  
   InItfirst,  
   InItlast  
);  
  
VectorView(  
   std::initializer_list<T> il  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `InIt`  
 現在の VectorView を初期化するために使用されるオブジェクトのコレクションの型。  
  
 il  
 A [std::initializer_list](../standard-library/initializer-list-class.md)要素が、VectorView を初期化するために適用されます。  
  
 `N`  
 現在の VectorView を初期化するために使用されるオブジェクトのコレクションの要素数。  
  
 `size`  
 VectorView の要素数。  
  
 `value`  
 現在の VectorView の各要素を初期化するために使用される値。  
  
 `v`  
 [Lvalues と Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)を[std::vector](../standard-library/vector-class.md)現在の VectorView を初期化するために使用されます。  
  
 `ptr`  
 現在の VectorView を初期化するために使用される `std::vector` へのポインター。  
  
 `arr`  
 A [platform::array](../cppcx/platform-array-class.md)現在の VectorView を初期化するために使用されるオブジェクト。  
  
 `a`  
 A [std::array](../standard-library/array-class-stl.md)現在の VectorView を初期化するために使用されるオブジェクト。  
  
 `first`  
 現在の VectorView を初期化するために使用されるオブジェクトのシーケンスの最初の要素。 型`first`によって渡される*完全転送*します。 詳細については、「[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md)」を参照してください。  
  
 `last`  
 現在の VectorView を初期化するために使用されるオブジェクトのシーケンスの最後の要素。 型`last`によって渡される*完全転送*します。 詳細については、「[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md)」を参照してください。  
  


  
## <a name="see-also"></a>関連項目  
 [プラットフォーム Namespace](platform-namespace-c-cx.md)   
 [C++ で Windows ランタイム コンポーネントの作成](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)