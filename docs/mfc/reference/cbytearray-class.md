---
title: CByteArray クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CByteArray
- AFXCOLL/CByteArray
- AFXCOLL/CObArray::CObArray
- AFXCOLL/CObArray::Add
- AFXCOLL/CObArray::Append
- AFXCOLL/CObArray::Copy
- AFXCOLL/CObArray::ElementAt
- AFXCOLL/CObArray::FreeExtra
- AFXCOLL/CObArray::GetAt
- AFXCOLL/CObArray::GetCount
- AFXCOLL/CObArray::GetData
- AFXCOLL/CObArray::GetSize
- AFXCOLL/CObArray::GetUpperBound
- AFXCOLL/CObArray::InsertAt
- AFXCOLL/CObArray::IsEmpty
- AFXCOLL/CObArray::RemoveAll
- AFXCOLL/CObArray::RemoveAt
- AFXCOLL/CObArray::SetAt
- AFXCOLL/CObArray::SetAtGrow
- AFXCOLL/CObArray::SetSize
dev_langs:
- C++
helpviewer_keywords:
- CObArray [MFC], CObArray
- CObArray [MFC], Add
- CObArray [MFC], Append
- CObArray [MFC], Copy
- CObArray [MFC], ElementAt
- CObArray [MFC], FreeExtra
- CObArray [MFC], GetAt
- CObArray [MFC], GetCount
- CObArray [MFC], GetData
- CObArray [MFC], GetSize
- CObArray [MFC], GetUpperBound
- CObArray [MFC], InsertAt
- CObArray [MFC], IsEmpty
- CObArray [MFC], RemoveAll
- CObArray [MFC], RemoveAt
- CObArray [MFC], SetAt
- CObArray [MFC], SetAtGrow
- CObArray [MFC], SetSize
ms.assetid: 53d4a512-657c-4187-9609-e3f5339a78e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e729c01d768d7ad74673b140496433ab73cf1f8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33352936"
---
# <a name="cbytearray-class"></a>CByteArray クラス
バイトの動的配列をサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CByteArray : public CObject  
```  
  
## <a name="members"></a>メンバー  
 メンバー関数は、`CByteArray`クラスのメンバー関数に似ています[CObArray](../../mfc/reference/cobarray-class.md)です。 メンバー関数については `CObArray` クラスの説明を参照してください。 任意の場所が表示、`CObject`ポインター関数パラメーターまたは戻り値は、置換、**バイト**です。  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 たとえば、次のように変換します。  
  
 `BYTE CByteArray::GetAt( int <nIndex> ) const;`  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CObArray::CObArray](../../mfc/reference/cobarray-class.md#cobarray)|空の配列を生成します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CObArray::Add](../../mfc/reference/cobarray-class.md#add)|配列の末尾に要素を追加します。必要に応じて、配列を大きくします。|  
|[CObArray::Append](../../mfc/reference/cobarray-class.md#append)|配列に別の配列を追加します。必要に応じて、配列を大きくします。|  
|[CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)|配列に別の配列をコピーします。必要に応じて、配列を大きくします。|  
|[CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)|配列内のバイトまでの一時的な参照を返します。|  
|[CObArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|現在の上限を超えている未使用のメモリをすべて解放します。|  
|[CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|指定されたインデックス位置にある値を返します。|  
|[CObArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|この配列内の要素の数を取得します。|  
|[CObArray::GetData](../../mfc/reference/cobarray-class.md#getdata)|配列内の要素へのアクセスを許可します。 指定できます**NULL**です。|  
|[CObArray::GetSize](../../mfc/reference/cobarray-class.md#getsize)|この配列内の要素の数を取得します。|  
|[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|有効な最大のインデックスを返します。|  
|[CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)|指定されたインデックス位置に要素 (または別の配列内のすべての要素) を挿入します。|  
|[CObArray::IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|配列が空かどうかを判別します。|  
|[CObArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|この配列からすべての要素を削除します。|  
|[CObArray::RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|特定のインデックス位置にある要素を削除します。|  
|[CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)|指定されたインデックスの値を設定します。配列は大きくできません。|  
|[CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|指定されたインデックスの値を設定します。必要に応じて、配列を大きくします。|  
|[CObArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|この配列に含まれる要素の数を設定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CObArray::operator](../../mfc/reference/cobarray-class.md#operator_at)|指定されたインデックス位置にある要素を設定または取得します。|  
  
## <a name="remarks"></a>コメント  
 `CByteArray` には、`IMPLEMENT_SERIAL` マクロが組み込まれており、その要素のシリアル化とダンプがサポートされます。 アーカイブをオーバー ロードされた出力ストリームにバイトの配列が格納されている場合 ( **<<**) 演算子、または、`Serialize`メンバー関数は、各要素は、逆に、シリアル化します。  
  
> [!NOTE]
>  配列を使用する前に、`SetSize` を使用してそのサイズを設定し、メモリを割り当てます。 `SetSize` を使用しない場合、配列に要素を追加すると、配列の再割り当てとコピーが頻繁に発生します。 頻繁な再割り当てとコピーは非効率であり、メモリが断片化される可能性があります。  
  
 配列内の個々 の要素からの出力をデバッグする必要がある場合は、深さを設定する必要があります、`CDumpContext`を 1 以上のオブジェクト。  
  
 使用する方法についての`CByteArray`、記事を参照して[コレクション](../../mfc/collections.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CByteArray`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcoll.h  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CObArray クラス](../../mfc/reference/cobarray-class.md)
