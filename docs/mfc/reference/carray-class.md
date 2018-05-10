---
title: CArray クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CArray
- AFXTEMPL/CArray
- AFXTEMPL/CArray::CArray
- AFXTEMPL/CArray::Add
- AFXTEMPL/CArray::Append
- AFXTEMPL/CArray::Copy
- AFXTEMPL/CArray::ElementAt
- AFXTEMPL/CArray::FreeExtra
- AFXTEMPL/CArray::GetAt
- AFXTEMPL/CArray::GetCount
- AFXTEMPL/CArray::GetData
- AFXTEMPL/CArray::GetSize
- AFXTEMPL/CArray::GetUpperBound
- AFXTEMPL/CArray::InsertAt
- AFXTEMPL/CArray::IsEmpty
- AFXTEMPL/CArray::RemoveAll
- AFXTEMPL/CArray::RemoveAt
- AFXTEMPL/CArray::SetAt
- AFXTEMPL/CArray::SetAtGrow
- AFXTEMPL/CArray::SetSize
dev_langs:
- CPP
helpviewer_keywords:
- CArray [MFC], CArray
- CArray [MFC], Add
- CArray [MFC], Append
- CArray [MFC], Copy
- CArray [MFC], ElementAt
- CArray [MFC], FreeExtra
- CArray [MFC], GetAt
- CArray [MFC], GetCount
- CArray [MFC], GetData
- CArray [MFC], GetSize
- CArray [MFC], GetUpperBound
- CArray [MFC], InsertAt
- CArray [MFC], IsEmpty
- CArray [MFC], RemoveAll
- CArray [MFC], RemoveAt
- CArray [MFC], SetAt
- CArray [MFC], SetAtGrow
- CArray [MFC], SetSize
ms.assetid: fead8b00-4cfd-4625-ad0e-251df62ba92f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4e4e4fd0106687927706b0ba303035258de7e651
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="carray-class"></a>CArray クラス
C 言語の配列に似ていますが動的を減らし、必要に応じて大きくなる配列をサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
template <class TYPE, class ARG_TYPE = const TYPE&>  
class CArray : public CObject  
```  
  
#### <a name="parameters"></a>パラメーター  
 `TYPE`  
 配列に格納されているオブジェクトの種類を指定するテンプレート パラメーター。 `TYPE` によって返されるパラメーターは、`CArray`です。  
  
 `ARG` *_* `TYPE`  
 配列に格納されているオブジェクトへのアクセスに使用される引数の型を指定するテンプレート パラメーター。 参照を多くの場合、`TYPE`です。 `ARG_TYPE` 渡されるパラメーターは、`CArray`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CArray::CArray](#carray)|空の配列を生成します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CArray::Add](#add)|配列の末尾に要素を追加します。必要に応じて、配列を大きくします。|  
|[CArray::Append](#append)|別の配列を追加します。必要に応じて、配列を大きく|  
|[CArray::Copy](#copy)|配列に別の配列をコピーします。必要に応じて、配列を大きくします。|  
|[CArray::ElementAt](#elementat)|配列内の要素ポインターへの一時的な参照を返します。|  
|[CArray::FreeExtra](#freeextra)|現在の上限を超えている未使用のメモリをすべて解放します。|  
|[CArray::GetAt](#getat)|指定されたインデックス位置にある値を返します。|  
|[呼び出す](#getcount)|この配列内の要素の数を取得します。|  
|[CArray::GetData](#getdata)|配列内の要素へのアクセスを許可します。 指定できます**NULL**です。|  
|[呼び出す](#getsize)|この配列内の要素の数を取得します。|  
|[CArray::GetUpperBound](#getupperbound)|有効な最大のインデックスを返します。|  
|[CArray::InsertAt](#insertat)|指定されたインデックス位置に要素 (または別の配列内のすべての要素) を挿入します。|  
|[CArray::IsEmpty](#isempty)|配列が空かどうかを判断します。|  
|[CArray::RemoveAll](#removeall)|この配列からすべての要素を削除します。|  
|[CArray::RemoveAt](#removeat)|特定のインデックス位置にある要素を削除します。|  
|[CArray::SetAt](#setat)|指定されたインデックスの値を設定します。配列は大きくできません。|  
|[CArray::SetAtGrow](#setatgrow)|指定されたインデックスの値を設定します。必要に応じて、配列を大きくします。|  
|[CArray::SetSize](#setsize)|この配列に含まれる要素の数を設定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator&#91;&#93;](#operator_at)|指定されたインデックス位置にある要素を設定または取得します。|  
  
## <a name="remarks"></a>コメント  
 配列のインデックスは、常に 0 の位置から開始します。 上限の境界を修正するか、過去の現在のバインド要素を追加するとき、展開先の配列を有効にするかどうかを決定できます。 上限の境界にメモリの割り当てが連続して場合でも、一部の要素が null になります。  
  
> [!NOTE]
>  サイズが変更されるほとんどのメソッド、`CArray`オブジェクトまたは要素を使用して追加[memcpy_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md)要素を移動します。 これは問題`memcpy_s`に呼び出されるコンス トラクターを必要とする任意のオブジェクトと互換性がありません。 場合内の項目、`CArray`と互換性がない`memcpy_s`、新規に作成する必要があります`CArray`適切なサイズ。 使用して[CArray::Copy](#copy)と[CArray::SetAt](#setat)これらのメソッドの代わりに、代入演算子を使用するために、新しい配列を作成する`memcpy_s`です。  
  
 C 言語の配列では、アクセスする時間と同様、`CArray`インデックス付けされた要素は定数とは、配列のサイズに依存しません。  
  
> [!TIP]
>  使用して配列を使用する前に[SetSize](#setsize)そのサイズを設定し、メモリを割り当てます。 `SetSize` を使用しない場合、配列に要素を追加すると、配列の再割り当てとコピーが頻繁に発生します。 頻繁な再割り当てとコピーは非効率であり、メモリが断片化される可能性があります。  
  
 配列内の個々 の要素のダンプを必要がある場合は、深さを設定する必要があります、 [CDumpContext](../../mfc/reference/cdumpcontext-class.md)を 1 以上のオブジェクト。  
  
 ほとんどの用途のグローバルのヘルパー関数をこのクラスの呼び出しの一部のメンバー関数をカスタマイズする必要があります、`CArray`クラスです。 トピックを参照して[コレクション クラスのヘルパー](../../mfc/reference/collection-class-helpers.md) MFC マクロとグローバルの「します。  
  
 配列クラスの派生は、リストの派生に似ています。  
  
 使用する方法の詳細についての`CArray`、記事を参照して[コレクション](../../mfc/collections.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CArray`  
  
## <a name="requirements"></a>要件  
 `Header:` afxtempl.h  
  
##  <a name="add"></a>  CArray::Add  
 新しい要素を配列の 1 つずつ拡張、配列の末尾に追加します。  
  
```  
INT_PTR Add(ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 `ARG_TYPE`  
 この配列内の要素を参照する引数の型を指定するテンプレート パラメーター。  
  
 `newElement`  
 この配列に追加する要素。  
  
### <a name="return-value"></a>戻り値  
 追加された要素のインデックス。  
  
### <a name="remarks"></a>コメント  
 場合[SetSize](#setsize)と共に使用した、 `nGrowBy` 1、余分なメモリよりも大きい値を割り当てることができます。 ただし、上限の境界がのみ 1 ずつ増加します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#22](../../mfc/codesnippet/cpp/carray-class_1.cpp)]  
  
##  <a name="append"></a>  CArray::Append  
 別の end に 1 つの配列の内容を追加するには、このメンバー関数を呼び出します。  
  
```  
INT_PTR Append(const CArray& src);
```  
  
### <a name="parameters"></a>パラメーター  
 *src*  
 配列に追加する要素のソースです。  
  
### <a name="return-value"></a>戻り値  
 追加の最初の要素のインデックス。  
  
### <a name="remarks"></a>コメント  
 配列は、同じ型でなければなりません。  
  
 必要に応じて、 **Append**配列に追加された要素を格納する余分なメモリを割り当てることがあります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#23](../../mfc/codesnippet/cpp/carray-class_2.cpp)]  
  
##  <a name="carray"></a>  CArray::CArray  
 空の配列を生成します。  
  
```  
CArray();
```  
  
### <a name="remarks"></a>コメント  
 配列は、一度に 1 つの要素を拡張します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#24](../../mfc/codesnippet/cpp/carray-class_3.cpp)]  
  
##  <a name="copy"></a>  CArray::Copy  
 1 つの配列の要素をコピーするのにには、このメンバー関数を使用します。  
  
```  
void Copy(const CArray& src);
```  
  
### <a name="parameters"></a>パラメーター  
 *src*  
 配列にコピーする要素のソースです。  
  
### <a name="remarks"></a>コメント  
 別の配列の要素と 1 つの配列の要素を上書きするには、このメンバー関数を呼び出します。  
  
 **コピー**メモリを解放しません。 ただし、必要に応じて、**コピー**配列にコピーされた要素を格納する余分なメモリを割り当てることがあります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#25](../../mfc/codesnippet/cpp/carray-class_4.cpp)]  
  
##  <a name="elementat"></a>  CArray::ElementAt  
 一時参照、配列内の指定した要素を返します。  
  
```  
TYPE& ElementAt(INT_PTR nIndex);  
const TYPE& ElementAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 0 以上である整数インデックスによって返された値以下[です](#getupperbound)です。  
  
### <a name="return-value"></a>戻り値  
 配列要素への参照。  
  
### <a name="remarks"></a>コメント  
 配列の左側の代入演算子の実装に使用されます。  
  
### <a name="example"></a>例  
  例を参照して[GetSize](#getsize)です。  
  
##  <a name="freeextra"></a>  CArray::FreeExtra  
 配列が拡張されたときに割り当てられたすべての余分なメモリを解放します。  
  
```  
void FreeExtra();
```  
  
### <a name="remarks"></a>コメント  
 この関数には、サイズや配列の上限値には影響はありません。  
  
### <a name="example"></a>例  
  例を参照して[GetData](#getdata)です。  
  
##  <a name="getat"></a>  CArray::GetAt  
 指定したインデックスにある配列要素を返します。  
  
```  
TYPE& GetAt(INT_PTR nIndex);  
const TYPE& GetAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 配列の要素の型を指定するテンプレート パラメーター。  
  
 `nIndex`  
 0 以上である整数インデックスによって返された値以下[です](#getupperbound)です。  
  
### <a name="return-value"></a>戻り値  
 指定したインデックス位置の配列要素。  
  
### <a name="remarks"></a>コメント  
 によって返される値よりも大きい負の値または値を渡す`GetUpperBound`アサーションは失敗が発生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#26](../../mfc/codesnippet/cpp/carray-class_5.cpp)]  
  
##  <a name="getcount"></a>  呼び出す  
 配列要素の数を返します。  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 配列内の項目の数。  
  
### <a name="remarks"></a>コメント  
 配列内の要素の数を取得するには、このメソッドを呼び出します。 インデックスが 0 から始まるため、サイズは、インデックスの最大値より大きい 1 です。 このメソッドを呼び出すのと同じ結果が生成されます、[呼び出す](#getsize)メソッドです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#27](../../mfc/codesnippet/cpp/carray-class_6.cpp)]  
  
##  <a name="getdata"></a>  CArray::GetData  
 このメンバー関数を配列内の要素に直接アクセスするために使用します。  
  
```  
const TYPE* GetData() const; 
TYPE* GetData();
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 配列の要素の型を指定するテンプレート パラメーター。  
  
### <a name="return-value"></a>戻り値  
 配列要素へのポインター。  
  
### <a name="remarks"></a>コメント  
 要素がない場合、 `GetData` null 値を返します。  
  
 呼び出すときに警告を使用して、配列の要素に直接アクセスより迅速に作業する際に役立つ、 `GetData`; 直接行うすべてのエラー、配列の要素に影響します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#28](../../mfc/codesnippet/cpp/carray-class_7.cpp)]  
  
##  <a name="getsize"></a>  呼び出す  
 配列のサイズを返します。  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="remarks"></a>コメント  
 インデックスが 0 から始まるため、サイズは、インデックスの最大値より大きい 1 です。 このメソッドを呼び出すのと同じ結果が生成されます、[呼び出す](#getcount)メソッドです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#29](../../mfc/codesnippet/cpp/carray-class_8.cpp)]  
  
##  <a name="getupperbound"></a>  CArray::GetUpperBound  
 この配列の現在の上限を返します。  
  
```  
INT_PTR GetUpperBound() const;  
```  
  
### <a name="remarks"></a>コメント  
 配列のインデックスは 0 から始まる、ために、この関数は値 1 を返しますより小さい`GetSize`です。  
  
 条件**です ()** =-1 は、配列に要素が含まれていないことを示します。  
  
### <a name="example"></a>例  
  例を参照して[CArray::GetAt](#getat)です。  
  
##  <a name="insertat"></a>  CArray::InsertAt  
 最初のバージョンの`InsertAt`配列内の指定したインデックス位置 1 つの要素 (または要素の複数のコピー) を挿入します。  
  
```  
void InsertAt(
    INT_PTR nIndex,
    ARG_TYPE newElement,  
    INT_PTR nCount = 1);
 
void InsertAt(
    INT_PTR nStartIndex,  
    CArray* pNewArray);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 によって返される値よりも大きい可能性がある整数インデックス`GetUpperBound`です。  
  
 `ARG_TYPE`  
 この配列内の要素の型を指定するテンプレート パラメーター。  
  
 `newElement`  
 この配列に格納される要素。  
  
 `nCount`  
 この要素にする必要があります回数には、(既定値 1) が挿入されます。  
  
 `nStartIndex`  
 によって返される値よりも大きい可能性がある整数インデックス[です](#getupperbound)です。  
  
 `pNewArray`  
 この配列に追加する要素を含む別の配列。  
  
### <a name="remarks"></a>コメント  
 プロセスでは、その上がり、(インデックスをインクリメント) によって、このインデックスでは、およびその位置にある既存の要素が上のすべての要素をシフトします。  
  
 2 番目のバージョンから別のすべての要素の挿入`CArray`開始位置として、コレクション、`nStartIndex`位置。  
  
 `SetAt`関数の場合、これに対し、1 つの指定した配列の要素を置換し、すべての要素を移動しません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#30](../../mfc/codesnippet/cpp/carray-class_9.cpp)]  
  
##  <a name="isempty"></a>  CArray::IsEmpty  
 配列が空かどうかを判断します。  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>戻り値  
 配列に要素が含まれていない場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="operator_at"></a>  CArray::operator \[\]  
 これらの添字演算子は便利な代替には、 [SetAt](#setat)と[GetAt](#getat)関数。  
  
```  
TYPE& operator[](int_ptr nindex);  
const TYPE& operator[](int_ptr nindex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *TYPE*  
 この配列内の要素の型を指定するテンプレート パラメーター。  
  
 `nIndex`  
 アクセスして、要素のインデックス。  
  
### <a name="remarks"></a>コメント  
 配列の最初の演算子が呼び出されます**const**右側の (右辺値) または代入ステートメントの左側 (左辺値) のいずれかで使用することがあります。 2 つ目と呼ばれる**const**配列は右側でのみ使用できます。  
  
 ライブラリのデバッグ バージョンでは、(いずれかで、左または代入ステートメントの右側にある)、添字が範囲外かどうかをアサートします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#34](../../mfc/codesnippet/cpp/carray-class_10.cpp)]  
  
##  <a name="relocateelements"></a>  CArray::RelocateElements  
 新しいバッファーにデータを再配置と配列は、拡大または縮小する必要があります。  
  
```  
template<class TYPE, class ARG_TYPE>  
AFX_INLINE void CArray<TYPE, ARG_TYPE>::RelocateElements(
    TYPE* pNewData,  
    const TYPE* pData,  
    INT_PTR nCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `pNewData`  
 要素の配列の新しいバッファーです。  
  
 `pData`  
 要素の古い配列。  
  
 `nCount`  
 元の配列要素の数。  
  
### <a name="remarks"></a>コメント  
 `pNewData` すべてを保持するのに十分な大きさでは常に、`pData`要素。  
  
 [CArray](../../mfc/reference/carray-class.md)実装では、このメソッドを使用して、配列の拡大または縮小する必要があるときに、古いデータを新しいバッファーにコピー (ときに[SetSize](#setsize)または[FreeExtra](#freeextra)と呼ばれます)。 既定の実装は、データだけをコピーします。  
  
 要素には、独自のメンバーのいずれかへのポインターが含まれています。 または、別の構造体は、配列要素のいずれかへのポインターを含む配列、ポインターは既定のコピーでは更新されません。 この場合、特殊化を実装することでポインターを修正できます`RelocateElements`に関連する型。 データのコピーを行う必要があります。  
  
##  <a name="removeall"></a>  CArray::RemoveAll  
 この配列からすべての要素を削除します。  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>コメント  
 配列が空では既に、関数は引き続き動作します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#31](../../mfc/codesnippet/cpp/carray-class_11.cpp)]  
  
##  <a name="removeat"></a>  CArray::RemoveAt  
 配列内の指定したインデックスから始まる 1 つまたは複数の要素を削除します。  
  
```  
void RemoveAt(
    INT_PTR nIndex,  
    INT_PTR nCount = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 0 以上である整数インデックスによって返された値以下[です](#getupperbound)です。  
  
 `nCount`  
 削除する要素の数を指定します。  
  
### <a name="remarks"></a>コメント  
 プロセスでは、削除された要素の上のすべての要素の下にシフトします。 これは、上は、配列のバインドしますが、メモリを解放しませんをデクリメントします。  
  
 削除位置以降の配列に含まれる以上の要素を削除しようとすると、ライブラリのデバッグ バージョンがアサートします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#32](../../mfc/codesnippet/cpp/carray-class_12.cpp)]  
  
##  <a name="setat"></a>  CArray::SetAt  
 指定したインデックス位置にある配列要素を設定します。  
  
```  
void SetAt(INT_PTR nIndex, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 0 以上である整数インデックスによって返された値以下[です](#getupperbound)です。  
  
 `ARG_TYPE`  
 配列の要素を参照するために使用する引数の型を指定するテンプレート パラメーター。  
  
 `newElement`  
 指定した位置に格納される新しい要素の値。  
  
### <a name="remarks"></a>コメント  
 `SetAt` 拡張する配列は発生しません。 使用して[SetAtGrow](#setatgrow)する場合は自動的に拡張する配列。  
  
 インデックスの値が配列内の有効な位置を表すことを確認する必要があります。 範囲外の場合は、ライブラリのデバッグ バージョンはアサートします。  
  
### <a name="example"></a>例  
  例を参照して[GetAt](#getat)です。  
  
##  <a name="setatgrow"></a>  CArray::SetAtGrow  
 指定したインデックス位置にある配列要素を設定します。  
  
```  
void SetAtGrow(INT_PTR nIndex, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 0 以上である整数のインデックス。  
  
 `ARG_TYPE`  
 配列内の要素の型を指定するテンプレート パラメーター。  
  
 `newElement`  
 この配列に追加する要素。 A **NULL**値は許可します。  
  
### <a name="remarks"></a>コメント  
 必要な場合に、配列が自動的に大きくなる (つまり、上限の境界から新しい要素のために調整されます)。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#33](../../mfc/codesnippet/cpp/carray-class_13.cpp)]  
  
##  <a name="setsize"></a>  CArray::SetSize  
 空であるか既存の配列のサイズを設定します必要な場合は、メモリを割り当てます。  
  
```  
void SetSize(
    INT_PTR nNewSize,  
    INT_PTR nGrowBy = -1);
```  
  
### <a name="parameters"></a>パラメーター  
 `nNewSize`  
 新しい配列のサイズ (要素の数)。 0 以上にする必要があります。  
  
 `nGrowBy`  
 サイズの増加が必要な場合を確保する要素のスロットの最小数。  
  
### <a name="remarks"></a>コメント  
 新しいサイズが前のサイズよりも小さい場合は、配列は切り捨てられ、すべての未使用メモリを解放します。  
  
 この関数を使用すると、配列を使用して開始する前に、配列のサイズを設定できます。 `SetSize` を使用しない場合、配列に要素を追加すると、配列の再割り当てとコピーが頻繁に発生します。 頻繁な再割り当てとコピーは非効率であり、メモリが断片化される可能性があります。  
  
 `nGrowBy`パラメーターは配列が拡大しているときに内部メモリの割り当てに影響します。 使用することはありませんに影響を与える、配列のサイズによって報告された[GetSize](#getsize)と[です](#getupperbound)です。 既定値を使用する場合、MFC はメモリの断片化を回避し、ほとんどの場合の効率を最適化するように計算にメモリを割り当てます。  
  
### <a name="example"></a>例  
  例を参照して[GetData](#getdata)です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプルの収集](../../visual-cpp-samples.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CObArray クラス](../../mfc/reference/cobarray-class.md)   
 [コレクション クラスのヘルパー](../../mfc/reference/collection-class-helpers.md)
