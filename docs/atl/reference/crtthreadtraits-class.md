---
title: CRTThreadTraits クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CRTThreadTraits
- ATLBASE/ATL::CRTThreadTraits
- ATLBASE/ATL::CRTThreadTraits::CreateThread
dev_langs:
- C++
helpviewer_keywords:
- CRTThreadTraits class
- threading [ATL], creation functions
- threading [ATL], CRT threads
ms.assetid: eb6e20b0-c2aa-4170-8e34-aaeeacc86343
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f08f0d6ea57aa5a153d190b357785911e64d6f09
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358167"
---
# <a name="crtthreadtraits-class"></a>CRTThreadTraits クラス
このクラスは、CRT のスレッドの作成機能を提供します。 スレッドが CRT 関数を使用する場合は、このクラスを使用します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CRTThreadTraits
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRTThreadTraits::CreateThread](#createthread)|(静的)この関数では、CRT 関数を使用するスレッドを作成します。|  
  
## <a name="remarks"></a>コメント  
 スレッドの特徴 (traits) は、特定の種類のスレッドの作成機能を提供するクラスです。 作成関数は、Windows と同じ署名とセマンティクスを持ちます[CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453)関数。  
  
 スレッドの特徴 (traits) は、次のクラスによって使用されます。  
  
- [CThreadPool](../../atl/reference/cthreadpool-class.md)  
  
- [使用](../../atl/reference/cworkerthread-class.md)  
  
 場合は、スレッドがありますを使用していない CRT 関数を使用して[Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md)代わりにします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="createthread"></a>  CRTThreadTraits::CreateThread  
 この関数では、CRT 関数を使用するスレッドを作成します。  
  
```
static HANDLE CreateThread(
    LPSECURITY_ATTRIBUTES lpsa,
    DWORD dwStackSize,
    LPTHREAD_START_ROUTINE pfnThreadProc,
    void* pvParam,
    DWORD dwCreationFlags,
    DWORD* pdwThreadId) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpsa`  
 新しいスレッドのセキュリティ属性。  
  
 `dwStackSize`  
 新しいスレッドのスタック サイズ。  
  
 `pfnThreadProc`  
 新しいスレッドのスレッド プロシージャです。  
  
 `pvParam`  
 スレッド プロシージャに渡されるパラメーター。  
  
 `dwCreationFlags`  
 (0 または CREATE_SUSPENDED) フラグを作成します。  
  
 `pdwThreadId`  
 [out]成功した場合、新しく作成されたスレッドのスレッド ID を受け取る DWORD 変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 エラー発生時に、新しく作成されたスレッドにハンドルを返します。 呼び出す[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)拡張エラー情報を取得します。  
  
### <a name="remarks"></a>コメント  
 参照してください[CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453)この関数に対するパラメーターの詳細についてはします。  
  
 この関数が呼び出す[_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md)スレッドを作成します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
