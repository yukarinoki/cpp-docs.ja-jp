---
title: インターフェイス
ms.date: 11/04/2016
f1_keywords:
- IWorkerThreadClient
- ATLUTIL/ATL::IWorkerThreadClient
- ATLUTIL/ATL::CloseHandle
- ATLUTIL/ATL::Execute
helpviewer_keywords:
- IWorkerThreadClient interface
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
ms.openlocfilehash: 6a68f25f153a0ad2cf42ebfaa374ff63c5746fcd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326309"
---
# <a name="iworkerthreadclient-interface"></a>インターフェイス

`IWorkerThreadClient`は[、CWorkerThread](../../atl/reference/cworkerthread-class.md)クラスのクライアントによって実装されるインターフェイスです。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
__interface IWorkerThreadClient
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[ハンドルを閉じる](#closehandle)|このメソッドを実装して、このオブジェクトに関連付けられているハンドルを閉じます。|
|[実行](#execute)|このオブジェクトに関連付けられたハンドルがシグナル状態になったときにコードを実行するには、このメソッドを実装します。|

## <a name="remarks"></a>解説

シグナル状態になるハンドルに応答してワーカー スレッドで実行する必要があるコードがある場合は、このインターフェイスを実装します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlutil.h

## <a name="iworkerthreadclientclosehandle"></a><a name="closehandle"></a>を閉じる

このメソッドを実装して、このオブジェクトに関連付けられているハンドルを閉じます。

```
HRESULT CloseHandle(HANDLE  hHandle);
```

### <a name="parameters"></a>パラメーター

*hハンドル*<br/>
閉じるハンドル。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

このメソッドに渡されたハンドルは、以前は[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)への呼び出しによってこのオブジェクトに関連付けられていた。

### <a name="example"></a>例

次のコードは、 の簡単`IWorkerThreadClient::CloseHandle`な実装を示しています。

[!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]

## <a name="iworkerthreadclientexecute"></a><a name="execute"></a>を実行します。

このオブジェクトに関連付けられたハンドルがシグナル状態になったときにコードを実行するには、このメソッドを実装します。

```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```

### <a name="parameters"></a>パラメーター

*ドウパラム*<br/>
ユーザー パラメーター。

*hオブジェクト*<br/>
シグナル状態になったハンドル。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

このメソッドに渡されたハンドルと DWORD/ポインターは、以前は[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)への呼び出しによってこのオブジェクトに関連付けされていました。

### <a name="example"></a>例

次のコードは、 の簡単`IWorkerThreadClient::Execute`な実装を示しています。

[!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/atl-classes.md)<br/>
[クラス](../../atl/reference/cworkerthread-class.md)
