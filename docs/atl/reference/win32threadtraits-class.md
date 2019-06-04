---
title: Win32ThreadTraits クラス
ms.date: 11/04/2016
f1_keywords:
- Win32ThreadTraits
- ATLBASE/ATL::Win32ThreadTraits
- ATLBASE/ATL::Win32ThreadTraits::CreateThread
helpviewer_keywords:
- threading [ATL], Windows threads
- threading [ATL], creation functions
- Win32ThreadTraits class
ms.assetid: 50279c38-eae1-4301-9ea6-97ccea580f3e
ms.openlocfilehash: cae5faea7938918da2656e21648282c1a2e1a66d
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503755"
---
# <a name="win32threadtraits-class"></a>Win32ThreadTraits クラス

このクラスは、Windows のスレッドの作成機能を提供します。 スレッドの CRT 関数を使用しない場合は、このクラスを使用します。

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
|[Win32ThreadTraits::CreateThread](#createthread)|(静的)CRT 関数を使用する必要がありますいないスレッドを作成するには、この関数を呼び出します。|

## <a name="remarks"></a>Remarks

スレッドの特徴は、特定の種類のスレッドの作成機能を提供するクラスです。 作成関数、Windows と同じシグネチャとセマンティクスを持ちます[CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread)関数。

スレッドの特徴は、次のクラスによって使用されます。

- [CThreadPool](../../atl/reference/cthreadpool-class.md)

- [CWorkerThread](../../atl/reference/cworkerthread-class.md)

場合は、スレッドは CRT 関数を使用して、使用して、 [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md)代わりにします。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

##  <a name="createthread"></a>  Win32ThreadTraits::CreateThread

CRT 関数を使用する必要がありますいないスレッドを作成するには、この関数を呼び出します。

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

*lpsa*<br/>
新しいスレッドのセキュリティ属性。

*dwStackSize*<br/>
新しいスレッドのスタック サイズ。

*pfnThreadProc*<br/>
新しいスレッドのスレッド プロシージャです。

*pvParam*<br/>
スレッド プロシージャに渡されるパラメーター。

*dwCreationFlags*<br/>
作成フラグ (0 または CREATE_SUSPENDED) を設定します。

*pdwThreadId*<br/>
[out]成功した場合、新しく作成されたスレッドのスレッド ID を受け取る DWORD 変数のアドレス。

### <a name="return-value"></a>戻り値

失敗した場合、新しく作成されたスレッドにハンドルを返します。 呼び出す[GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror)拡張エラー情報を取得します。

### <a name="remarks"></a>Remarks

参照してください[CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread)詳細については、この関数のパラメーター。

この関数を呼び出す`CreateThread`スレッドを作成します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
