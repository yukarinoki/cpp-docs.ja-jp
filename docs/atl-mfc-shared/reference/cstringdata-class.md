---
title: CStringData クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStringData
- ATLSIMPSTR/ATL::CStringData
- ATLSIMPSTR/ATL::AddRef
- ATLSIMPSTR/ATL::data
- ATLSIMPSTR/ATL::IsLocked
- ATLSIMPSTR/ATL::IsShared
- ATLSIMPSTR/ATL::Lock
- ATLSIMPSTR/ATL::Release
- ATLSIMPSTR/ATL::Unlock
- ATLSIMPSTR/ATL::nAllocLength
- ATLSIMPSTR/ATL::nDataLength
- ATLSIMPSTR/ATL::nRefs
- ATLSIMPSTR/ATL::pStringMgr
dev_langs:
- C++
helpviewer_keywords:
- CStringData class
- shared classes, CStringData
ms.assetid: 4e31b5ca-3dbe-4fd5-b692-8211fbfb2593
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 187892b74536de47079324d90bb21b2569e00498
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363572"
---
# <a name="cstringdata-class"></a>CStringData クラス
このクラスは、文字列オブジェクトのデータを表します。  
  
## <a name="syntax"></a>構文  
  
```
struct CStringData
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[AddRef](#addref)|文字列データ オブジェクトの参照カウントをインクリメントします。|  
|[data](#data)|文字列オブジェクトの文字データを取得します。|  
|[IsLocked](#islocked)|関連付けられている文字列オブジェクトのバッファーがロックされているかどうかを判断します。|  
|[とき](#isshared)|関連付けられている文字列オブジェクトのバッファーが現在共有かどうかを判断します。|  
|[ロック](#lock)|関連付けられている文字列オブジェクトのバッファーをロックします。|  
|[Release](#release)|指定された文字列オブジェクトを解放します。|  
|[ロックを解除します。](#unlock)|関連付けられている文字列オブジェクトのバッファーがアンロックされます。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|[nAllocLength](#nalloclength)|割り当てられているデータの長さ`XCHAR`(終端の null) 含まない s|  
|[nDataLength](#ndatalength)|現在使用されているデータの長さ`XCHAR`(終端の null) 含まない s|  
|[nRefs](#nrefs)|オブジェクトの現在の参照カウントします。|  
|[pStringMgr](#pstringmgr)|この文字列オブジェクトの文字列のマネージャーへのポインター。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、カスタム文字列マネージャーを実装している開発者でのみ使用する必要があります。 カスタム文字列マネージャーの詳細については、次を参照してください[メモリ管理と CStringT。](../../atl-mfc-shared/memory-management-with-cstringt.md)  
  
 このクラスは、さまざまな種類の情報およびなどの上位の文字列オブジェクトに関連付けられているデータをカプセル化[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)、 [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)、または[CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)オブジェクト。 上位のすべての文字列オブジェクトがそれに関連するへのポインターを含む`CStringData`オブジェクト、同じ文字列のデータ オブジェクトをポイントする複数の文字列オブジェクトを許可します。 このリレーションシップは、参照カウントによって表されます ( `nRefs`) の`CStringData`オブジェクト。  
  
> [!NOTE]
>  特定の場合、文字列型 (など**CFixedString**) は、上位 2 つ以上の文字列オブジェクトを文字列データ オブジェクトを共有していません。 詳細については、次を参照してください。[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)です。  
  
 このデータで構成されます。  
  
-   メモリ マネージャー (型の[IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)) の文字列。  
  
-   現在の長さ ( [nDataLength](#ndatalength)) の文字列。  
  
-   割り当て済みの長さ ( [nAllocLength](#nalloclength)) の文字列。 パフォーマンス上の理由から、この異なることが現在の文字列の長さ  
  
-   現在の参照カウント ( [nRefs](#nrefs)) の`CStringData`オブジェクト。 この値は文字列オブジェクトの数は同じ共有を決定するときに使用`CStringData`オブジェクト。  
  
-   実際の文字バッファー ([データ](#data)) の文字列。  
  
    > [!NOTE]
    >  文字列オブジェクトの実際の文字バッファー文字列マネージャーが割り当てられるし、に追加されますが、`CStringData`オブジェクト。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsimpstr.h  
  
##  <a name="addref"></a>  CStringData::AddRef  
 文字列オブジェクトの参照カウントをインクリメントします。  
  
```
void AddRef() throw();
```  
  
### <a name="remarks"></a>コメント  
 文字列オブジェクトの参照カウントをインクリメントします。  
  
> [!NOTE]
>  負の数は、文字列バッファーがロックされていることを示すために、負の値の参照カウントを持つ文字列をこのメソッドを呼び出さないでください。  
  
##  <a name="data"></a>  CStringData::data  
 文字列オブジェクトの文字バッファーへのポインターを返します。  
  
```
void* data() throw();
```  
  
### <a name="return-value"></a>戻り値  
 文字列オブジェクトの文字バッファーへのポインター。  
  
### <a name="remarks"></a>コメント  
 この関数では、関連付けられている文字列オブジェクトの現在の文字バッファーを返します。  
  
> [!NOTE]
>  このバッファーはによって割り当てられていない、`CStringData`オブジェクトが必要なときに、文字列マネージャーによってです。 割り当てられるバッファーは文字列データ オブジェクトに追加されます。  
  
##  <a name="islocked"></a>  CStringData::IsLocked  
 文字バッファーがロックされているかどうかを判断します。  
  
```
bool IsLocked() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します**true**バッファーがロックされている、それ以外の場合**false**です。  
  
### <a name="remarks"></a>コメント  
 文字列オブジェクトの文字バッファーがロックされているかどうかを判断するには、この関数を呼び出します。  
  
##  <a name="isshared"></a>  CStringData::IsShared  
 文字バッファーを共有するかどうかを判断します。  
  
```
bool IsShared() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します**true**バッファーが共有それ以外の場合は**false**です。  
  
### <a name="remarks"></a>コメント  
 かどうか、文字列データ オブジェクトの文字バッファー共有されている複数の文字列オブジェクトを決定するには、この関数を呼び出します。  
  
##  <a name="lock"></a>  CStringData::Lock  
 関連付けられている文字列オブジェクトの文字バッファーをロックします。  
  
```
void Lock() throw();
```  
  
### <a name="remarks"></a>コメント  
 文字列データ オブジェクトの文字バッファーをロックするには、この関数を呼び出します。 ロックおよびロック解除は、開発者が文字バッファーへの直接アクセスが必要な場合に使用されます。 ロックの良い例が示される、 [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer)と[として](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer)のメソッド`CSimpleStringT`です。  
  
> [!NOTE]
>  バッファーが上位の文字列オブジェクトの間で共有されていない場合のみ、文字バッファーをロックできます。  
  
##  <a name="nalloclength"></a>  CStringData::nAllocLength  
 割り当てられた文字バッファーの長さです。  
  
```
int nAllocLength;
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているデータのバッファーの長さを格納`XCHAR`s (終端の null) などではありません。  
  
##  <a name="ndatalength"></a>  CStringData::nDataLength  
 現在の string オブジェクトの長さ。  
  
```
int nDataLength;
```  
  
### <a name="remarks"></a>コメント  
 現在使用されているデータの長さを格納`XCHAR`s (終端の null) などではありません。  
  
##  <a name="nrefs"></a>  CStringData::nRefs  
 文字列データ オブジェクトの参照カウント。  
  
```
long nRefs;
```  
  
### <a name="remarks"></a>コメント  
 文字列データ オブジェクトの参照カウントを格納します。 この数は、文字列データ オブジェクトに関連付けられている上位の文字列オブジェクトの数を示します。 負の値は、文字列データ オブジェクトが現在ロックされていることを示します。  
  
##  <a name="pstringmgr"></a>  CStringData::pStringMgr  
 関連付けられている文字列オブジェクトのメモリ マネージャー。  
  
```
IAtlStringMgr* pStringMgr;
```  
  
### <a name="remarks"></a>コメント  
 関連付けられている文字列オブジェクトのメモリ マネージャーを格納します。 メモリ マネージャーおよび文字列の詳細については、次を参照してください。[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)です。  
  
##  <a name="release"></a>  CStringData::Release  
 データの文字列オブジェクトの参照カウントをデクリメントします。  
  
```
void Release() throw();
```  
  
### <a name="remarks"></a>コメント  
 参照カウントをデクリメントするためには、この関数を呼び出す解放、`CStringData`場合は、参照カウントがゼロの構造体します。 文字列オブジェクトが削除され、必要がなくなった文字列データ オブジェクトを参照するときにこれが一般的です。  
  
 たとえば、次のコードは呼び出します`CStringData::Release`文字列データ オブジェクトに関連付けられたの`str1`:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#104](../../atl-mfc-shared/codesnippet/cpp/cstringdata-class_1.cpp)]  
  
##  <a name="unlock"></a>  CStringData::Unlock  
 関連付けられている文字列オブジェクトの文字バッファーがアンロックされます。  
  
```
void Unlock() throw();
```  
  
### <a name="remarks"></a>コメント  
 文字列データ オブジェクトの文字バッファーのロックを解除するには、この関数を呼び出します。 バッファーはロックされているが、共有可能であるし、参照をカウントできます。  
  
> [!NOTE]
>  各呼び出し`Lock`への対応する呼び出しで一致する必要があります`Unlock`です。  
  
 開発者は、文字列データを共有しないことを確認する必要がありますロックおよびロック解除が使用されます。 ロックの良い例が示される、 [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer)と[として](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer)のメソッド`CSimpleStringT`です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)


