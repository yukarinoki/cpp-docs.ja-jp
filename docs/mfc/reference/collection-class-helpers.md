---
title: コレクション クラスのヘルパー |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.classes
dev_langs:
- C++
helpviewer_keywords:
- DestructElements function
- ConstructElements function
- SerializeElements function
- collection classes [MFC], helper functions
- helper functions collection class [MFC]
ms.assetid: bc3a2368-9edd-4748-9e6a-13cba79517ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d00d78acf7ddf8cfa27e117cbcdbbb00c7d6fa6b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="collection-class-helpers"></a>コレクション クラスのヘルパー
コレクション クラス`CMap`、 `CList`、および`CArray`を比較する、コピー、および要素をシリアル化するためにグローバル テンプレートのヘルパー関数を使用します。 基づくクラスの実装の一部として`CMap`、 `CList`、および`CArray`マップ、リスト、または配列に格納されたデータの種類に合うように、必要に応じて、これらの関数をオーバーライドする必要があります。 などのヘルパー関数を上書きする方法について`SerializeElements`、記事を参照して[コレクション: タイプ セーフなコレクションを作成する方法](../../mfc/how-to-make-a-type-safe-collection.md)です。 なお**ConstructElements**と**DestructElements**使用されなくなりました。  
  
 Microsoft Foundation Class ライブラリでは、afxtempl.h のコレクション クラスをカスタマイズするための次のグローバル関数を提供します。  
  
### <a name="collection-class-helpers"></a>コレクション クラスのヘルパー  
  
|||  
|-|-|  
|[CompareElements](#compareelements)|要素は、同じかどうかを示します。|  
|[CopyElements](#copyelements)|別の 1 つの配列から要素をコピーします。|  
|[DumpElements](#dumpelements)|ストリーム指向の診断出力を提供します。|  
|[HashKey](#hashkey)|ハッシュ キーを計算します。|  
|[SerializeElements](#serializeelements)|保存またはアーカイブからの要素を取得します。|  
  
##  <a name="compareelements"></a>  CompareElements  
 によって直接呼び出されます。 [CList::Find] (clist class.md #not_found.md #clist__find と間接的に[cmap__lookup](cmap-class.md#lookup)と[cmap__operator &#91; &#93;](cmap-class.md#operator_at)です。  
  
```   
template<class TYPE, class ARG_TYPE>  
BOOL AFXAPI  
CompareElements(
    const TYPE* pElement1,  
    const ARG_TYPE* pElement2);  
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 比較する最初の要素の型。  
  
 `pElement1`  
 比較する最初の要素へのポインター。  
  
 `ARG_TYPE`  
 比較する 2 番目の要素の型。  
  
 `pElement2`  
 比較する 2 番目の要素へのポインター。  
  
### <a name="return-value"></a>戻り値  
 オブジェクトを指す場合は 0 以外`pElement1`が指すオブジェクトと等しい`pElement2`。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 `CMap`使用を呼び出し、`CMap`テンプレート パラメーター*キー*と`ARG_KEY`です。  
  
 既定の実装の比較の結果を返します *\*pElement1*と *\*pElement2*です。 アプリケーションの適切な方法で要素を比較できるように、この関数をオーバーライドします。  
  
 C++ 言語には、比較演算子が定義されています ( `==`) 単純型の場合 ( `char`、 `int`、 **float**など) クラスおよび構造体の比較演算子が定義されていません。 使用する場合`CompareElements`それを使用するコレクション クラスの 1 つのインスタンスを作成、比較演算子を定義するか、オーバー ロードまたは`CompareElements`バージョン適切な値を返しますを使用します。  
  
### <a name="requirements"></a>要件  
   **ヘッダー:** afxtempl.h   
  
##  <a name="copyelements"></a>  CopyElements  
 この関数が直接呼び出された[CArray::Append](carray-class.md#append)と[CArray::Copy](carray-class.md#copy)です。  
  
```   
template<class TYPE>  
void AFXAPI CopyElements(
    TYPE* pDest,  
    const TYPE* pSrc,  
    INT_PTR nCount);  
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 コピーする要素の型を指定するテンプレート パラメーター。  
  
 `pDest`  
 要素のコピー先へのポインター。  
  
 `pSrc`  
 コピーする要素のソースへのポインター。  
  
 `nCount`  
 コピーする要素の数。  
  
### <a name="remarks"></a>コメント  
 既定の実装は、単純な代入演算子を使用して ( **=** )、コピー操作を実行します。 コピーされた型がオーバー ロードされた演算子 =、既定の実装は、ビットごとのコピーを実行します。  
  
 この関数およびその他のヘルパー関数を実装する方法については、記事を参照してください。[コレクション: タイプ セーフなコレクションを作成する方法](../how-to-make-a-type-safe-collection.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxtempl.h  
  
##  <a name="dumpelements"></a>  DumpElements  
 オーバーライドされた場合、コレクションの要素のテキスト形式のストリーム指向の診断出力を提供します。  
  
```   
template<class TYPE>  
void  AFXAPI DumpElements(
    CDumpContext& dc,  
    const TYPE* pElements,  
    INT_PTR nCount);  
```  
  
### <a name="parameters"></a>パラメーター  
 `dc`  
 要素をダンプするためのコンテキストをダンプします。  
  
 *TYPE*  
 要素の型を指定するテンプレート パラメーター。  
  
 `pElements`  
 ダンプする要素を指すポインター。  
  
 `nCount`  
 ダンプする要素の数。  
  
### <a name="remarks"></a>コメント  
 **CArray::Dump**、 **CList::Dump**、および**CMap::Dump**関数を呼び出すこのダンプの深さは 0 より大きい場合。  
  
 既定の実装では、何も行われません。 場合は、コレクションの要素から派生`CObject`を呼び出してオーバーライドは通常、コレクションの要素を反復処理する`Dump`ターンの各要素に対してです。  
  

### <a name="requirements"></a>要件  
  **ヘッダー** afxtempl.h  
  
##  <a name="hashkey"></a>  HashKey  
 指定したキーのハッシュ値を計算します。  
  
```  
template<class ARG_KEY>  
AFX_INLINE UINT AFXAPI HashKey(ARG_KEY  key); 
```  
  
### <a name="parameters"></a>パラメーター  
 `ARG_KEY`  
 マップ キーにアクセスするために使用するデータ型を指定するテンプレート パラメーター。  
  
 `key`  
 ハッシュ値が計算されるキー。  
  
### <a name="return-value"></a>戻り値  
 キーのハッシュ値。  
  
### <a name="remarks"></a>コメント  
 この関数が直接呼び出された[CMap::RemoveKey](cmap-class.md#removekey)および間接的に[CMap::Lookup](cmap-class.md#lookup)と[CMap::Operator &#91; &#93;](cmap-class.md#operator_at)です。
  
 既定の実装では、ハッシュ値を作成脱却しつつ`key`して 4 つの位置。 アプリケーションに適したハッシュ値を返すように、この関数をオーバーライドします。  
  
### <a name="example"></a>例
 ```cpp  
template <> UINT AFXAPI HashKey(unsigned __int64 key)
{
   // Generate the hash value by XORing the lower 32 bits of the number 
   // with the upper 32 bits
   return(UINT(key) ^ UINT(key >> 32));
}
 ```
 
### <a name="requirements"></a>要件  
  **ヘッダー** afxtempl.h 
  
##  <a name="serializeelements"></a>  SerializeElements  
 [CArray](carray-class.md)、 [CList](clist-class.md)、および[CMap](cmap-class.md)要素をシリアル化するには、この関数を呼び出します。  
  
```   
template<class TYPE>  
void AFXAPI SerializeElements(CArchive& ar, TYPE* pElements, INT_PTR nCount);  
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 要素の型を指定するテンプレート パラメーター。  
  
 `ar`  
 またはからにアーカイブするアーカイブ オブジェクト。  
  
 `pElements`  
 アーカイブされる要素へのポインター。  
  
 `nCount`  
 アーカイブされる要素の数  
  
### <a name="remarks"></a>コメント  
 既定の実装は、ビットごとの読み取りまたは書き込み。  
  
 この関数およびその他のヘルパー関数を実装する方法については、記事を参照してください。[コレクション: タイプ セーフなコレクションを作成する方法](../how-to-make-a-type-safe-collection.md)です。  
  
### <a name="example"></a>例  
 アーティクルの例を参照して[コレクション: タイプ セーフなコレクションを作成する方法](../how-to-make-a-type-safe-collection.md)です。  
 
### <a name="requirements"></a>要件  
  **ヘッダー** afxtempl.h 
    
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](mfc-macros-and-globals.md)   
 [CMap クラス](cmap-class.md)   
 [CList クラス](clist-class.md)   
 [CArray クラス](carray-class.md)