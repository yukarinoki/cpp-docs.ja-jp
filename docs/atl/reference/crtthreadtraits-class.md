---
title: CRTThreadTraits クラス |Microsoft Docs
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
ms.openlocfilehash: f58b5936ab9f73ce2fe351d078e61bddfda54d6c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097823"
---
# <a name="crtthreadtraits-class"></a>CRTThreadTraits クラス

このクラスは、CRT のスレッドの作成機能を提供します。 スレッドの CRT 関数が使用する場合は、このクラスを使用します。

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
|[CRTThreadTraits::CreateThread](#createthread)|(静的)CRT 関数を使用してスレッドを作成するには、この関数を呼び出します。|

## <a name="remarks"></a>Remarks

スレッドの特徴は、特定の種類のスレッドの作成機能を提供するクラスです。 作成関数、Windows と同じシグネチャとセマンティクスを持ちます[CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread)関数。

スレッドの特徴は、次のクラスによって使用されます。

- [CThreadPool](../../atl/reference/cthreadpool-class.md)

- [CWorkerThread](../../atl/reference/cworkerthread-class.md)

場合は、スレッドがありますを使用していない CRT 関数を使用して、 [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md)代わりにします。

## <a name="requirements"></a>要件

**ヘッダー:** atlbase.h

##  <a name="createthread"></a>  CRTThreadTraits::CreateThread

CRT 関数を使用してスレッドを作成するには、この関数を呼び出します。

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

*は、*<br/>
作成フラグ (0 または CREATE_SUSPENDED) を設定します。

*pdwThreadId*<br/>
[out]成功した場合、新しく作成されたスレッドのスレッド ID を受け取る DWORD 変数のアドレス。

### <a name="return-value"></a>戻り値

失敗した場合、新しく作成されたスレッドにハンドルを返します。 呼び出す[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)拡張エラー情報を取得します。

### <a name="remarks"></a>Remarks

参照してください[CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread)詳細については、この関数のパラメーター。

この関数を呼び出す[_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md)スレッドを作成します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
