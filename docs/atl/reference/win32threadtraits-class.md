---
title: クラス 32 スレッドトレイツ
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
ms.openlocfilehash: 64f02293508894a70f36c29d5032c9ba8f250c38
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325792"
---
# <a name="win32threadtraits-class"></a>クラス 32 スレッドトレイツ

このクラスは、Windows スレッドの作成関数を提供します。 スレッドが CRT 関数を使用しない場合は、このクラスを使用します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class Win32ThreadTraits
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を使用します。](#createthread)|(静的)CRT 関数を使用しないスレッドを作成します。|

## <a name="remarks"></a>解説

スレッドの特徴は、特定の種類のスレッドの作成関数を提供するクラスです。 作成関数には、Windows [CreateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread)関数と同じシグネチャとセマンティクスがあります。

スレッドの特徴は、次のクラスで使用されます。

- [CThreadPool](../../atl/reference/cthreadpool-class.md)

- [を行う](../../atl/reference/cworkerthread-class.md)

スレッドが CRT 関数を使用する場合は、代わりに[CRTThreadTraits を使用します](../../atl/reference/crtthreadtraits-class.md)。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="win32threadtraitscreatethread"></a><a name="createthread"></a>を使用します。

CRT 関数を使用しないスレッドを作成します。

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

*サイズを変更します。*<br/>
新しいスレッドのスタック サイズ。

*を実行します。*<br/>
新しいスレッドのスレッド プロシージャ。

*pvパラム*<br/>
スレッド プロシージャに渡すパラメーター。

*フラグを作成します。*<br/>
作成フラグ (0 またはCREATE_SUSPENDED)。

*をクリックします。*<br/>
[アウト]成功した場合に、新しく作成されたスレッドのスレッド ID を受け取る DWORD 変数のアドレス。

### <a name="return-value"></a>戻り値

新しく作成されたスレッドへのハンドルを返すか、失敗した場合は NULL を返します。 拡張エラー情報を取得するには[、GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)を呼び出します。

### <a name="remarks"></a>解説

この関数のパラメーターの詳細については[、CreateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread)を参照してください。

この関数は`CreateThread`、スレッドを作成するために呼び出します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
