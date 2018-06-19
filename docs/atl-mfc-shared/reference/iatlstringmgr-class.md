---
title: IAtlStringMgr クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- IAtlStringMgr
- ATLSIMPSTR/ATL::IAtlStringMgr
- ATLSIMPSTR/ATL::Allocate
- ATLSIMPSTR/ATL::Clone
- ATLSIMPSTR/ATL::Free
- ATLSIMPSTR/ATL::GetNilString
- ATLSIMPSTR/ATL::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- shared classes, IAtlStringMgr
- memory, managing
- IAtlStringMgr class
ms.assetid: 722f0346-a770-4aa7-8f94-177be8dba823
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 05d7ff0a38c0a557016887e6fce92fcb0bf28226
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360127"
---
# <a name="iatlstringmgr-class"></a>IAtlStringMgr クラス
このクラスにインターフェイスを表します、`CStringT`メモリ マネージャー。  
  
## <a name="syntax"></a>構文  
  
```
__interface IAtlStringMgr
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[割り当てる](#allocate)|新しい文字列データ構造を割り当てるには、このメソッドを呼び出します。|  
|[複製](#clone)|別のインスタンスで使用するための新しい文字列マネージャーへのポインターを返すには、このメソッドを呼び出す`CSimpleStringT`です。|  
|[無料](#free)|文字列データの構造体を解放するには、このメソッドを呼び出します。|  
|[GetNilString](#getnilstring)|ポインターを返します、`CStringData`空の文字列オブジェクトによって使用されるオブジェクト。|  
|[再割り当てします](#reallocate)|このメソッドを呼び出して、文字列データの構造を再割り当てください。|  
  
## <a name="remarks"></a>コメント  
 このインターフェイスは、MFC に依存しない文字列クラスによって使用されるメモリを管理します。ように[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)、 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)、および[CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)です。  
  
 このクラスを使用して、カスタム文字列クラスのカスタム メモリ マネージャーを実装することができますも。 詳細については、次を参照してください。[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsimpstr.h  
  
##  <a name="allocate"></a>  IAtlStringMgr::Allocate  
 新しい文字列データ構造体を割り当てます。  
  
```
CStringData* Allocate(int nAllocLength,int nCharSize) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nAllocLength`  
 新しいメモリ ブロック内の文字の数。  
  
 `nCharSize`  
 文字列マネージャーによって使用される文字型のサイズをバイト単位で。  
  
### <a name="return-value"></a>戻り値  
 新しく割り当てられたメモリ ブロックへのポインターを返します。  
  
> [!NOTE]
>  例外をスローして失敗した割り当てをシグナルされません。 失敗した割り当てを返すことによって通知される代わりに、 **NULL**です。  
  
### <a name="remarks"></a>コメント  
 呼び出す[IAtlStringMgr::Free](#free)または[IAtlStringMgr::ReAllocate](#reallocate)このメソッドによって割り当てられたメモリを解放します。  
  
> [!NOTE]
>  使用例については、次を参照してください。[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)です。  
  
##  <a name="clone"></a>  IAtlStringMgr::Clone  
 別のインスタンスで使用するための新しい文字列マネージャーへのポインターを返します`CSimpleStringT`です。  
  
```
IAtlStringMgr* Clone() throw();
```  
  
### <a name="return-value"></a>戻り値  
 コピーを返します、`IAtlStringMgr`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 よく文字列マネージャーが新しい文字列に必要な場合に、フレームワークによって呼び出されます ほとんどの場合、**この**ポインターが返されます。  
  
 ただし、メモリ マネージャーが複数のインスタンスによって使用されているをサポートしていない場合`CSimpleStringT`、共有可能な文字列のマネージャーへのポインターが返される必要があります。  
  
> [!NOTE]
>  使用例については、次を参照してください。[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)です。  
  
##  <a name="free"></a>  IAtlStringMgr::Free  
 文字列データの構造体を解放します。  
  
```
void Free(CStringData* pData) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pData`  
 解放するメモリ ブロックへのポインター。  
  
### <a name="remarks"></a>コメント  
 割り当てられている指定されたメモリ ブロックを解放[Allocate](#allocate)または[再割り当て](../../atl/reference/iatlmemmgr-class.md#reallocate)です。  
  
> [!NOTE]
>  使用例については、次を参照してください。[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)です。  
  
##  <a name="getnilstring"></a>  IAtlStringMgr::GetNilString  
 空の文字列を文字列データ構造体へのポインターを返します。  
  
```
CStringData* GetNilString() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CStringData`空の文字列を表すオブジェクトです。  
  
### <a name="remarks"></a>コメント  
 空の文字列表現を取得するには、この関数を呼び出します。  
  
> [!NOTE]
>  カスタム文字列マネージャーを実装するときにこの関数が失敗しない必要があります。 インスタンスに埋め込むことによってこれを確認できる**CNilStringData**文字列マネージャー クラスとそのインスタンスへのポインターを返すにします。  
  
> [!NOTE]
>  使用例については、次を参照してください。[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)です。  
  
##  <a name="reallocate"></a>  IAtlStringMgr::Reallocate  
 文字列データ構造を再割り当ています。  
  
```
CStringData* Reallocate(  
 CStringData* pData,
 int nAllocLength,
 int nCharSize) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pData`  
 このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。  
  
 `nAllocLength`  
 新しいメモリ ブロック内の文字の数。  
  
 `nCharSize`  
 文字列マネージャーによって使用される文字型のサイズをバイト単位で。  
  
### <a name="return-value"></a>戻り値  
 新しく割り当てられたメモリ ブロックの先頭へのポインターを返します。  
  
### <a name="remarks"></a>コメント  
 指定された既存のメモリ ブロックのサイズを変更するには、この関数を呼び出す`pData`です。  
  
 呼び出す[IAtlStringMgr::Free](#free)このメソッドによって割り当てられたメモリを解放します。  
  
> [!NOTE]
>  使用例については、次を参照してください。[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)


