---
title: CAtlAutoThreadModuleT クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT::GetDefaultThreads
dev_langs:
- C++
helpviewer_keywords:
- CAtlAutoThreadModuleT class
ms.assetid: ae1667c6-3fb8-47bc-b35d-9ea5e9896d7f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a54818b839f13ad9114274248cfdbfc74efa033a
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883074"
---
# <a name="catlautothreadmodulet-class"></a>CAtlAutoThreadModuleT クラス
このクラスは、スレッド プール、アパートメント モデルの COM サーバーを実装するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T, 
         class ThreadAllocator = CComSimpleThreadAllocator,
         DWORD dwWait = INFINITE>  
class ATL_NO_VTABLE CAtlAutoThreadModuleT : public IAtlAutoThreadModule
```  
  
#### <a name="parameters"></a>パラメーター  
 *T*  
 COM サーバーを実装するクラスです。  
  
 *テンプレートパラ*  
 スレッドの選択を管理するクラスです。 既定値は[CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)します。  
  
 *内部*  
 ミリ秒単位で、タイムアウト間隔を指定します。 既定値は、INFINITE で、決してメソッドのタイムアウト間隔が経過するとします。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlAutoThreadModuleT::GetDefaultThreads](#getdefaultthreads)|この静的関数は動的に計算し、プロセッサの数に基づいて、EXE モジュールのスレッドの最大数を返します。|  
  
## <a name="remarks"></a>Remarks  
 クラスは、 [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md)から派生した`CAtlAutoThreadModuleT`スレッド プール、アパートメント モデルの COM サーバーを実装するためにします。 古いクラスに置き換えられます[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)します。  
  
> [!NOTE]
>  既定値として、DLL でこのクラスが使用されない必要があります*内部*無限の値、DLL が読み込まれるとデッドロックが発生します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IAtlAutoThreadModule`  
  
 `CAtlAutoThreadModuleT`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlbase.h  
  
##  <a name="getdefaultthreads"></a>  CAtlAutoThreadModuleT::GetDefaultThreads  
 この静的関数は動的に計算し、プロセッサの数に基づいて、EXE モジュールのスレッドの最大数を返します。  
  
```
static int GetDefaultThreads();
```  
  
### <a name="return-value"></a>戻り値  
 EXE モジュール内に作成するスレッドの数。  
  
### <a name="remarks"></a>Remarks  
 スレッドの数を計算するための別の方法を使用する場合は、このメソッドをオーバーライドします。 既定では、スレッドの数がプロセッサの数に基づいています。  
  
## <a name="see-also"></a>関連項目  
 [IAtlAutoThreadModule クラス](../../atl/reference/iatlautothreadmodule-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [IAtlAutoThreadModule クラス](../../atl/reference/iatlautothreadmodule-class.md)   
 [モジュール クラス](../../atl/atl-module-classes.md)
