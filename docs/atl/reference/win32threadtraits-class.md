---
title: Win32ThreadTraits クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- Win32ThreadTraits
- ATLBASE/ATL::Win32ThreadTraits
- ATLBASE/ATL::Win32ThreadTraits::CreateThread
dev_langs:
- C++
helpviewer_keywords:
- threading [ATL], Windows threads
- threading [ATL], creation functions
- Win32ThreadTraits class
ms.assetid: 50279c38-eae1-4301-9ea6-97ccea580f3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b863808a2367cae8878728403dbf11265b9e819
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362017"
---
# <a name="win32threadtraits-class"></a>Win32ThreadTraits クラス
このクラスは、Windows のスレッドの作成機能を提供します。 スレッド CRT 関数を使用しない場合は、このクラスを使用します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class Win32ThreadTraits
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Win32ThreadTraits::CreateThread](#createthread)|(静的)この関数では、CRT 関数を使用しないで、スレッドを作成します。|  
  
## <a name="remarks"></a>コメント  
 スレッドの特徴 (traits) は、特定の種類のスレッドの作成機能を提供するクラスです。 作成関数は、Windows と同じ署名とセマンティクスを持ちます[CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453)関数。  
  
 スレッドの特徴 (traits) は、次のクラスによって使用されます。  
  
- [CThreadPool](../../atl/reference/cthreadpool-class.md)  
  
- [使用](../../atl/reference/cworkerthread-class.md)  
  
 使用する場合は、スレッドは CRT 関数を使用して、 [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md)代わりにします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="createthread"></a>  Win32ThreadTraits::CreateThread  
 この関数では、CRT 関数を使用しないで、スレッドを作成します。  
  
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
  
 この関数が呼び出す`CreateThread`スレッドを作成します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
