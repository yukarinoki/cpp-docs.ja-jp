---
title: グローバル関数をマーシャ リング |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlFreeMarshalStream
- atlbase/ATL::AtlMarshalPtrInProc
- atlbase/ATL::AtlUnmarshalPtr
dev_langs:
- C++
ms.assetid: 877100b5-6ad9-44c5-a2e0-09414f1720d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44c5205416ff19eeb849b0532d015275e4eb166e
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879340"
---
# <a name="marshaling-global-functions"></a>マーシャ リングに関するグローバル関数
これらの関数は、マーシャ リングとマーシャ リング データ インターフェイス ポインターに変換するサポートを提供します。  
  
> [!IMPORTANT]
>  Windows ランタイムで実行するアプリケーションでは、次の表に示す関数を使用できません。  
  
|||  
|-|-|  
|[AtlFreeMarshalStream](#atlfreemarshalstream)|マーシャ リング データを解放し、`IStream`ポインター。|  
|[AtlMarshalPtrInProc](#atlmarshalptrinproc)|新しいストリーム オブジェクトを作成し、指定されたインターフェイス ポインターをマーシャ リングします。|  
|[AtlUnmarshalPtr](#atlunmarshalptr)|インターフェイス ポインターには、ストリームのマーシャ リング データを変換します。|  

## <a name="requirements"></a>要件:
**ヘッダー:** atlbase.h
  
##  <a name="atlfreemarshalstream"></a>  AtlFreeMarshalStream  
 ストリーム内のマーシャリング データを解放し、次にストリーム ポインターも解放します。  

```
HRESULT AtlFreeMarshalStream(IStream* pStream);
```  
  
### <a name="parameters"></a>パラメーター  
 *pStream*  
 [in]ポインター、`IStream`インターフェイスのマーシャ リングするために使用するストリーム。  
  
### <a name="example"></a>例  
  例をご覧ください[AtlMarshalPtrInProc](#atlmarshalptrinproc)します。  
  
##  <a name="atlmarshalptrinproc"></a>  AtlMarshalPtrInProc  
 新しいストリーム オブジェクトを作成し、プロキシの CLSID をストリームに書き込みます。さらに、プロキシの初期化に必要なデータをストリームに書き込んで、指定されたインターフェイス ポインターをマーシャリングします。  
  
```
HRESULT AtlMarshalPtrInProc(
    IUnknown* pUnk,
    const IID& iid,
    IStream** ppStream);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 [in]マーシャ リングするインターフェイスへのポインター。  
  
 *iid*  
 [in]マーシャ リングされるインターフェイスの GUID です。  
  
 *ppStream*  
 [out]ポインター、`IStream`マーシャ リングするため、新しいストリーム オブジェクトのインターフェイス。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>Remarks  
 MSHLFLAGS_TABLESTRONG フラグは設定されているため、複数のストリームにポインターをマーシャ リングすることができます。 ポインターもいないマーシャ リングされた複数回できます。  
  
 失敗をマーシャ リングする場合は、ストリーム ポインターが解放されます。  
  
 `AtlMarshalPtrInProc` プロセスでオブジェクトへのポインターでのみ使用できます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#50](../../atl/codesnippet/cpp/marshaling-global-functions_1.cpp)]  
  
##  <a name="atlunmarshalptr"></a>  AtlUnmarshalPtr  
 ストリームのマーシャリング データをクライアントが使用できるインターフェイス ポインターに変換します。  
   
```
HRESULT AtlUnmarshalPtr(
    IStream* pStream,
    const IID& iid,
    IUnknown** ppUnk);
```  
  
### <a name="parameters"></a>パラメーター  
 *pStream*  
 [in]マーシャ リング解除されているストリームへのポインター。  
  
 *iid*  
 [in]マーシャ リング解除されているインターフェイスの GUID です。  
  
 *ppUnk*  
 [out]マーシャ リング解除されたインターフェイスへのポインター。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="example"></a>例  
  例をご覧ください[AtlMarshalPtrInProc](#atlmarshalptrinproc)します。  
  
## <a name="see-also"></a>関連項目  
 [関数](../../atl/reference/atl-functions.md)
