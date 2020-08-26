---
title: IWorkerThreadClient インターフェイス
ms.date: 11/04/2016
f1_keywords:
- IWorkerThreadClient
- ATLUTIL/ATL::IWorkerThreadClient
- ATLUTIL/ATL::CloseHandle
- ATLUTIL/ATL::Execute
helpviewer_keywords:
- IWorkerThreadClient interface
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
ms.openlocfilehash: aa72f090a006d6936339582a919b0faf5cab6b03
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835351"
---
# <a name="iworkerthreadclient-interface"></a>IWorkerThreadClient インターフェイス

`IWorkerThreadClient` は、 [CWorkerThread](../../atl/reference/cworkerthread-class.md) クラスのクライアントによって実装されるインターフェイスです。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
__interface IWorkerThreadClient
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|名前|説明|
|-|-|
|[CloseHandle](#closehandle)|このオブジェクトに関連付けられているハンドルを閉じるには、このメソッドを実装します。|
|[実行](#execute)|このオブジェクトに関連付けられたハンドルがシグナル状態になったときにコードを実行するには、このメソッドを実装します。|

## <a name="remarks"></a>解説

ハンドルがシグナル状態になると、ワーカースレッドで実行する必要があるコードがある場合は、このインターフェイスを実装します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlutil. h

## <a name="iworkerthreadclientclosehandle"></a><a name="closehandle"></a> IWorkerThreadClient:: CloseHandle

このオブジェクトに関連付けられているハンドルを閉じるには、このメソッドを実装します。

```
HRESULT CloseHandle(HANDLE  hHandle);
```

### <a name="parameters"></a>パラメーター

*hHandle*<br/>
閉じるハンドル。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

このメソッドに渡されたハンドルは、 [CWorkerThread:: AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)を呼び出すことによって、以前にこのオブジェクトに関連付けられていました。

### <a name="example"></a>例

次のコードは、の単純な実装を示して `IWorkerThreadClient::CloseHandle` います。

[!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]

## <a name="iworkerthreadclientexecute"></a><a name="execute"></a> IWorkerThreadClient:: Execute

このオブジェクトに関連付けられたハンドルがシグナル状態になったときにコードを実行するには、このメソッドを実装します。

```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```

### <a name="parameters"></a>パラメーター

*dwParam*<br/>
ユーザーパラメーター。

*hObject*<br/>
がシグナル状態になったハンドル。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

このメソッドに渡されたハンドルと DWORD/ポインターは、 [CWorkerThread:: AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)を呼び出すことによって、以前にこのオブジェクトに関連付けられていました。

### <a name="example"></a>例

次のコードは、の単純な実装を示して `IWorkerThreadClient::Execute` います。

[!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/atl-classes.md)<br/>
[CWorkerThread クラス](../../atl/reference/cworkerthread-class.md)
