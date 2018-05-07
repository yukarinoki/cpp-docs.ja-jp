---
title: CTypedPtrArray クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTypedPtrArray
- AFXTEMPL/CTypedPtrArray
- AFXTEMPL/CTypedPtrArray::Add
- AFXTEMPL/CTypedPtrArray::Append
- AFXTEMPL/CTypedPtrArray::Copy
- AFXTEMPL/CTypedPtrArray::ElementAt
- AFXTEMPL/CTypedPtrArray::GetAt
- AFXTEMPL/CTypedPtrArray::InsertAt
- AFXTEMPL/CTypedPtrArray::SetAt
- AFXTEMPL/CTypedPtrArray::SetAtGrow
dev_langs:
- C++
helpviewer_keywords:
- CTypedPtrArray [MFC], Add
- CTypedPtrArray [MFC], Append
- CTypedPtrArray [MFC], Copy
- CTypedPtrArray [MFC], ElementAt
- CTypedPtrArray [MFC], GetAt
- CTypedPtrArray [MFC], InsertAt
- CTypedPtrArray [MFC], SetAt
- CTypedPtrArray [MFC], SetAtGrow
ms.assetid: e3ecdf1a-a889-4156-92dd-ddbd36ccd919
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dbbe2d9ed6ab7a17ccbd110d12070d4e295a62ec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ctypedptrarray-class"></a>CTypedPtrArray クラス
`CPtrArray` クラスまたは `CObArray`クラスのオブジェクトに対してタイプセーフな "ラッパー" を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
template<class BASE_CLASS, class TYPE>  
class CTypedPtrArray : public BASE_CLASS  
```  
  
#### <a name="parameters"></a>パラメーター  
 `BASE_CLASS`  
 クラスの基本クラス、型付きポインター配列です。配列クラスである必要があります (`CObArray`または`CPtrArray`)。  
  
 `TYPE`  
 基本クラスの配列に格納されている要素の型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CTypedPtrArray::Add](#add)|新しい要素を配列の末尾に追加します。 必要に応じて、配列を大きく|  
|[CTypedPtrArray::Append](#append)|1 つの配列の内容を別の末尾に追加します。 必要に応じて、配列を大きく|  
|[CTypedPtrArray::Copy](#copy)|配列に別の配列をコピーします。必要に応じて、配列を大きくします。|  
|[CTypedPtrArray::ElementAt](#elementat)|配列内の要素ポインターへの一時的な参照を返します。|  
|[CTypedPtrArray::GetAt](#getat)|指定されたインデックス位置にある値を返します。|  
|[CTypedPtrArray::InsertAt](#insertat)|指定されたインデックス位置に要素 (または別の配列内のすべての要素) を挿入します。|  
|[CTypedPtrArray::SetAt](#setat)|指定されたインデックスの値を設定します。配列は大きくできません。|  
|[CTypedPtrArray::SetAtGrow](#setatgrow)|指定されたインデックスの値を設定します。必要に応じて、配列を大きくします。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CTypedPtrArray::operator](#operator_at)|指定されたインデックス位置にある要素を設定または取得します。|  
  
## <a name="remarks"></a>コメント  
 使用すると`CTypedPtrArray`なく`CPtrArray`または`CObArray`C++ の型チェック機能は、一致していないポインター型によって発生したエラーを解消します。  
  
 さらに、`CTypedPtrArray`ラッパーを使用した場合に必要になるキャストの多くを実行します`CObArray`または`CPtrArray`です。  
  
 すべて`CTypedPtrArray`関数はインラインでこのテンプレートの使用が大幅には影響しません、コードの速度またはサイズ。  
  
 使用する方法についての`CTypedPtrArray`、記事を参照して[コレクション](../../mfc/collections.md)と[テンプレート ベースのクラス](../../mfc/template-based-classes.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `BASE_CLASS`  
  
 `CTypedPtrArray`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxtempl.h  
  
##  <a name="add"></a>  CTypedPtrArray::Add  
 このメンバー関数が呼び出す`BASE_CLASS` **:: 追加**です。  
  
```  
INT_PTR Add(TYPE newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 配列に追加する要素の型を指定するテンプレート パラメーター。  
  
 `newElement`  
 この配列に追加する要素。  
  
### <a name="return-value"></a>戻り値  
 追加された要素のインデックス。  
  
### <a name="remarks"></a>コメント  
 詳細についてを参照してください。 [CObArray::Add](../../mfc/reference/cobarray-class.md#add)です。  
  
##  <a name="append"></a>  CTypedPtrArray::Append  
 このメンバー関数が呼び出す`BASE_CLASS` **:: Append**です。  
  
```  
INT_PTR Append(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```  
  
### <a name="parameters"></a>パラメーター  
 `BASE_CLASS`  
 クラスの基本クラス、型付きポインター配列です。配列クラスである必要があります ( [CObArray](../../mfc/reference/cobarray-class.md)または[CPtrArray](../../mfc/reference/cptrarray-class.md))。  
  
 *TYPE*  
 基本クラスの配列に格納されている要素の型。  
  
 *src*  
 配列に追加する要素のソースです。  
  
### <a name="return-value"></a>戻り値  
 追加の最初の要素のインデックス。  
  
### <a name="remarks"></a>コメント  
 詳細についてを参照してください。 [CObArray::Append](../../mfc/reference/cobarray-class.md#append)です。  
  
##  <a name="copy"></a>  CTypedPtrArray::Copy  
 このメンバー関数が呼び出す`BASE_CLASS` **:: コピー**です。  
  
```  
void Copy(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```  
  
### <a name="parameters"></a>パラメーター  
 `BASE_CLASS`  
 クラスの基本クラス、型付きポインター配列です。配列クラスである必要があります ( [CObArray](../../mfc/reference/cobarray-class.md)または[CPtrArray](../../mfc/reference/cptrarray-class.md))。  
  
 *TYPE*  
 基本クラスの配列に格納されている要素の型。  
  
 *src*  
 配列にコピーする要素のソースです。  
  
### <a name="remarks"></a>コメント  
 詳細についてを参照してください。 [CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)です。  
  
##  <a name="elementat"></a>  CTypedPtrArray::ElementAt  
 このインライン関数が呼び出す`BASE_CLASS` **:: ElementAt**です。  
  
```  
TYPE& ElementAt(INT_PTR nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 この配列に格納されている要素の型を指定するテンプレート パラメーター。  
  
 `nIndex`  
 0 以上である整数インデックスによって返された値以下`BASE_CLASS` **:: です**です。  
  
### <a name="return-value"></a>戻り値  
 指定された場所にある要素への一時的な参照`nIndex`です。 この要素は、テンプレート パラメーターで指定された型*型*です。  
  
### <a name="remarks"></a>コメント  
 詳細についてを参照してください。 [CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)です。  
  
##  <a name="getat"></a>  CTypedPtrArray::GetAt  
 このインライン関数が呼び出す`BASE_CLASS` **:: GetAt**です。  
  
```  
TYPE GetAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 配列に格納されている要素の型を指定するテンプレート パラメーター。  
  
 `nIndex`  
 0 以上である整数インデックスによって返された値以下`BASE_CLASS` **:: です**です。  
  
### <a name="return-value"></a>戻り値  
 指定された位置にある要素のコピー`nIndex`です。 この要素は、テンプレート パラメーターで指定された型*型*です。  
  
### <a name="remarks"></a>コメント  
 詳細についてを参照してください[CObArray::GetAt。](../../mfc/reference/cobarray-class.md#getat)  
  
##  <a name="insertat"></a>  CTypedPtrArray::InsertAt  
 このメンバー関数が呼び出す`BASE_CLASS` **:: InsertAt**です。  
  
```  
void InsertAt(
    INT_PTR nIndex,  
    TYPE newElement,  
    INT_PTR nCount = 1);

 
void InsertAt(
    INT_PTR nStartIndex,  
    CTypedPtrArray<BASE_CLASS, TYPE>* pNewArray);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 によって返される値よりも大きい可能性がある整数インデックス[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)です。  
  
 *TYPE*  
 基本クラスの配列に格納されている要素の型。  
  
 `newElement`  
 この配列に格納されるオブジェクトのポインター。 A`newElement`値の**NULL**は許可されています。  
  
 `nCount`  
 この要素にする必要があります回数には、(既定値 1) が挿入されます。  
  
 `nStartIndex`  
 によって返される値よりも大きい可能性がある整数インデックス`CObArray::GetUpperBound`です。  
  
 `BASE_CLASS`  
 クラスの基本クラス、型付きポインター配列です。配列クラスである必要があります ( [CObArray](../../mfc/reference/cobarray-class.md)または[CPtrArray](../../mfc/reference/cptrarray-class.md))。  
  
 `pNewArray`  
 この配列に追加する要素を含む別の配列。  
  
### <a name="remarks"></a>コメント  
 詳細についてを参照してください。 [CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)です。  
  
##  <a name="operator_at"></a>  CTypedPtrArray::operator  
 これらの演算子のインラインを呼び出す`BASE_CLASS` **:: 演算子**です。  
  
```  
TYPE& operator[ ](int_ptr nindex);  
TYPE operator[ ](int_ptr nindex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 配列に格納されている要素の型を指定するテンプレート パラメーター。  
  
 `nIndex`  
 0 以上である整数インデックスによって返された値以下`BASE_CLASS` **:: です**です。  
  
### <a name="remarks"></a>コメント  
 配列の最初の演算子が呼び出されます**const**右側の (右辺値) または代入ステートメントの左側 (左辺値) のいずれかで使用できます。 呼び出される 2 番目、 **const**配列、右側にのみ使用できます。  
  
 ライブラリのデバッグ バージョンでは、(いずれかで、左または代入ステートメントの右側にある)、添字が範囲外かどうかをアサートします。  
  
##  <a name="setat"></a>  CTypedPtrArray::SetAt  
 このメンバー関数が呼び出す`BASE_CLASS` **:: SetAt**です。  
  
```  
void SetAt(
    INT_PTR nIndex,  
    TYPE ptr);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 0 以上である整数インデックスによって返された値以下[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)です。  
  
 *TYPE*  
 基本クラスの配列に格納されている要素の型。  
  
 *ptr*  
 配列、nIndex 位置に挿入される要素へのポインター。 NULL 値は許可されています。  
  
### <a name="remarks"></a>コメント  
 詳細についてを参照してください。 [CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)です。  
  
##  <a name="setatgrow"></a>  CTypedPtrArray::SetAtGrow  
 このメンバー関数が呼び出す`BASE_CLASS` **:: SetAtGrow**です。  
  
```  
void SetAtGrow(
    INT_PTR nIndex,  
    TYPE newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 0 以上である整数のインデックス。  
  
 *TYPE*  
 基本クラスの配列に格納されている要素の型。  
  
 `newElement`  
 この配列に追加するオブジェクトのポインター。 A **NULL**値は許可します。  
  
### <a name="remarks"></a>コメント  
 詳細についてを参照してください。 [CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプルの収集](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CPtrArray クラス](../../mfc/reference/cptrarray-class.md)   
 [CObArray クラス](../../mfc/reference/cobarray-class.md)
