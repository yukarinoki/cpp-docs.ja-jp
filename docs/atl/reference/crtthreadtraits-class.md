---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CRTThreadTraits
- ATLBASE/ATL::CRTThreadTraits
- ATLBASE/ATL::CRTThreadTraits::CreateThread
helpviewer_keywords:
- CRTThreadTraits class
- threading [ATL], creation functions
- threading [ATL], CRT threads
ms.assetid: eb6e20b0-c2aa-4170-8e34-aaeeacc86343
ms.openlocfilehash: a7cfddc64e8c1b4e192e718d05812e385fbe08ed
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331023"
---
# <a name="crtthreadtraits-class"></a>クラス

このクラスは CRT スレッドの作成関数を提供します。 スレッドが CRT 関数を使用する場合は、このクラスを使用します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CRTThreadTraits
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[スレッドトレイト::スレッドの作成](#createthread)|(静的)CRT 関数を使用できるスレッドを作成します。|

## <a name="remarks"></a>解説

スレッドの特徴は、特定の種類のスレッドの作成関数を提供するクラスです。 作成関数には、Windows [CreateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread)関数と同じシグネチャとセマンティクスがあります。

スレッドの特徴は、次のクラスで使用されます。

- [CThreadPool](../../atl/reference/cthreadpool-class.md)

- [を行う](../../atl/reference/cworkerthread-class.md)

スレッドが CRT 関数を使用しない場合は、代わりに[Win32ThreadTraits を使用します](../../atl/reference/win32threadtraits-class.md)。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="crtthreadtraitscreatethread"></a><a name="createthread"></a>スレッドトレイト::スレッドの作成

CRT 関数を使用できるスレッドを作成します。

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

この関数は[、_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md)を呼び出してスレッドを作成します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
