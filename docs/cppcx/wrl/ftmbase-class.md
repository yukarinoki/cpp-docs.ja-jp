---
title: FtmBase クラス
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase
- ftm/Microsoft::WRL::FtmBaseCreateGlobalInterfaceTable
- ftm/Microsoft::WRL::FtmBase::DisconnectObject
- ftm/Microsoft::WRL::FtmBase::FtmBase
- ftm/Microsoft::WRL::FtmBase::GetMarshalSizeMax
- ftm/Microsoft::WRL::FtmBase::GetUnmarshalClass
- ftm/Microsoft::WRL::FtmBase::MarshalInterface
- ftm/Microsoft::WRL::FtmBase::marshaller_
- ftm/Microsoft::WRL::FtmBase::ReleaseMarshalData
- ftm/Microsoft::WRL::FtmBase::UnmarshalInterface
helpviewer_keywords:
- Microsoft::WRL::FtmBase class
- Microsoft::WRL::FtmBase::CreateGlobalInterfaceTable method
- Microsoft::WRL::FtmBase::DisconnectObject method
- Microsoft::WRL::FtmBase::FtmBase, constructor
- Microsoft::WRL::FtmBase::GetMarshalSizeMax method
- Microsoft::WRL::FtmBase::GetUnmarshalClass method
- Microsoft::WRL::FtmBase::MarshalInterface method
- Microsoft::WRL::FtmBase::marshaller_ data member
- Microsoft::WRL::FtmBase::ReleaseMarshalData method
- Microsoft::WRL::FtmBase::UnmarshalInterface method
ms.assetid: 275f3b71-2975-4f92-89e7-d351e96496df
ms.openlocfilehash: f28a850c365bc9a75d8e5b100e5e5cc0a1c5dc10
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "86404565"
---
# <a name="ftmbase-class"></a>FtmBase クラス

フリー スレッド マーシャラー オブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
class FtmBase :
    public Microsoft::WRL::Implements<
        Microsoft::WRL::RuntimeClassFlags<WinRtClassicComMix>,
        Microsoft::WRL::CloakedIid<IMarshal>
    >;
```

## <a name="remarks"></a>解説

詳細については、「 [RuntimeClass クラス](runtimeclass-class.md)」を参照してください。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

| 名前                         | 説明                                        |
| ---------------------------- | -------------------------------------------------- |
| [FtmBase:: FtmBase](#ftmbase) | `FtmBase` クラスの新しいインスタンスを初期化します。 |

### <a name="public-methods"></a>パブリック メソッド

| 名前                                                               | 説明                                                                                                                                                          |
| ------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [FtmBase:: CreateGlobalInterfaceTable](#createglobalinterfacetable) | グローバルインターフェイステーブル (GIT) を作成します。                                                                                                                              |
| [FtmBase::D Isの Tobject](#disconnectobject)                     | オブジェクトへのすべての外部接続を強制的に解放します。 オブジェクトのサーバーは、シャットダウンする前に、このメソッドのオブジェクトの実装を呼び出します。                |
| [FtmBase:: GetMarshalSizeMax](#getmarshalsizemax)                   | 指定したオブジェクトで、指定したインターフェイスポインターをマーシャリングするために必要なバイト数の上限を取得します。                                                |
| [FtmBase:: GetUnmarshalClass](#getunmarshalclass)                   | COM が、対応するプロキシのコードを含む DLL を検索するために使用する CLSID を取得します。 COM は、この DLL を読み込み、初期化されていないプロキシインスタンスを作成します。 |
| [FtmBase:: MarshalInterface](#marshalinterface)                     | 一部のクライアントプロセスでプロキシオブジェクトを初期化するために必要なデータをストリームに書き込みます。                                                                          |
| [FtmBase:: ReleaseMarshalData](#releasemarshaldata)                 | マーシャリング済みのデータパケットを破棄します。                                                                                                                                    |
| [FtmBase:: UnmarshalInterface](#unmarshalinterface)                 | 新しく作成されたプロキシを初期化し、そのプロキシへのインターフェイスポインターを返します。                                                                                    |

### <a name="public-data-members"></a>パブリック データ メンバー

| 名前                                | 説明                                       |
| ----------------------------------- | ------------------------------------------------- |
| [FtmBase:: marshaller_](#marshaller) | フリースレッドマーシャラーへの参照を保持します。 |

## <a name="inheritance-hierarchy"></a>継承階層

`FtmBase`

## <a name="requirements"></a>必要条件

**ヘッダー:** ftm

**名前空間:** Microsoft::WRL

## <a name="ftmbasecreateglobalinterfacetable"></a><a name="createglobalinterfacetable"></a>FtmBase:: CreateGlobalInterfaceTable

グローバルインターフェイステーブル (GIT) を作成します。

```cpp
static HRESULT CreateGlobalInterfaceTable(
   __out IGlobalInterfaceTable **git
);
```

### <a name="parameters"></a>パラメーター

*git*<br/>
この操作が完了したときに、グローバルインターフェイステーブルへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

### <a name="remarks"></a>解説

詳細については、「[`IGlobalInterfaceTable`](https://docs.microsoft.com/windows/win32/api/objidl/nn-objidl-iglobalinterfacetable)」を参照してください。

## <a name="ftmbasedisconnectobject"></a><a name="disconnectobject"></a>FtmBase::D Isの Tobject

オブジェクトへのすべての外部接続を強制的に解放します。 オブジェクトのサーバーは、シャットダウンする前に、このメソッドのオブジェクトの実装を呼び出します。

```cpp
STDMETHODIMP DisconnectObject(
   __in DWORD dwReserved
) override;
```

### <a name="parameters"></a>パラメーター

*dwReserved*<br/>
今後使用するために予約されています。0 にする必要があります。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="ftmbaseftmbase"></a><a name="ftmbase"></a>FtmBase:: FtmBase

`FtmBase` クラスの新しいインスタンスを初期化します。

```cpp
FtmBase();
```

## <a name="ftmbasegetmarshalsizemax"></a><a name="getmarshalsizemax"></a>FtmBase:: GetMarshalSizeMax

指定したオブジェクトで、指定したインターフェイスポインターをマーシャリングするために必要なバイト数の上限を取得します。

```cpp
STDMETHODIMP GetMarshalSizeMax(
   __in REFIID riid,
   __in_opt void *pv,
   __in DWORD dwDestContext,
   __reserved void *pvDestContext,
   __in DWORD mshlflags,
   __out DWORD *pSize
) override;
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
マーシャリングするインターフェイスの識別子への参照。

*pv*<br/>
マーシャリングされるインターフェイスポインター。NULL を指定できます。

*dwDestContext*<br/>
指定したインターフェイスのマーシャリングを解除するターゲットコンテキスト。

1つまたは複数の MSHCTX 列挙値を指定します。

現在、マーシャリング解除は、現在のプロセスの別のアパートメント (MSHCTX_INPROC)、または現在のプロセスと同じコンピューター上の別のプロセス (MSHCTX_LOCAL) のいずれかで発生する可能性があります。

*pvDestContext*<br/>
将来使用するために予約されています。NULL にする必要があります。

*mshlflags*<br/>
マーシャリングされるデータをクライアントプロセスに送り返すかどうかを示すフラグです。一般的なケースでは、複数のクライアントから取得できるグローバルテーブルに書き込まれます。 1つまたは複数の MSHLFLAGS 列挙値を指定します。

*pSize*<br/>
この操作が完了すると、マーシャリングストリームに書き込まれるデータ量の上限を指すポインターになります。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、E_FAIL または E_NOINTERFACE ます。

## <a name="ftmbasegetunmarshalclass"></a><a name="getunmarshalclass"></a>FtmBase:: GetUnmarshalClass

COM が、対応するプロキシのコードを含む DLL を検索するために使用する CLSID を取得します。 COM は、この DLL を読み込み、初期化されていないプロキシインスタンスを作成します。

```cpp
STDMETHODIMP GetUnmarshalClass(
   __in REFIID riid,
   __in_opt void *pv,
   __in DWORD dwDestContext,
   __reserved void *pvDestContext,
   __in DWORD mshlflags,
   __out CLSID *pCid
) override;
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
マーシャリングするインターフェイスの識別子への参照。

*pv*<br/>
マーシャリングするインターフェイスへのポインター。呼び出し元が目的のインターフェイスへのポインターを持っていない場合は、NULL にすることができます。

*dwDestContext*<br/>
指定したインターフェイスのマーシャリングを解除するターゲットコンテキスト。

1つまたは複数の MSHCTX 列挙値を指定します。

マーシャリング解除は、現在のプロセスの別のアパートメント (MSHCTX_INPROC)、または現在のプロセスと同じコンピューター上の別のプロセス (MSHCTX_LOCAL) のいずれかで発生する可能性があります。

*pvDestContext*<br/>
将来使用するために予約されています。NULL にする必要があります。

*mshlflags*<br/>
この操作が完了したら、クライアントプロセスでプロキシを作成するために使用する CLSID へのポインター。

*pCid*

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、S_FALSE ます。

## <a name="ftmbasemarshalinterface"></a><a name="marshalinterface"></a>FtmBase:: MarshalInterface

一部のクライアントプロセスでプロキシオブジェクトを初期化するために必要なデータをストリームに書き込みます。

```cpp
STDMETHODIMP MarshalInterface(
   __in IStream *pStm,
   __in REFIID riid,
   __in_opt void *pv,
   __in DWORD dwDestContext,
   __reserved void *pvDestContext,
   __in DWORD mshlflags
) override;
```

### <a name="parameters"></a>パラメーター

*pStm*<br/>
マーシャリング中に使用されるストリームへのポインター。

*riid*<br/>
マーシャリングするインターフェイスの識別子への参照。 このインターフェイスは、 `IUnknown` インターフェイスから派生する必要があります。

*pv*<br/>
マーシャリングするインターフェイスポインターへのポインター。呼び出し元が目的のインターフェイスへのポインターを持っていない場合は、NULL にすることができます。

*dwDestContext*<br/>
指定したインターフェイスのマーシャリングを解除するターゲットコンテキスト。

1つまたは複数の MSHCTX 列挙値を指定します。

マーシャリング解除は、現在のプロセスの別のアパートメント (MSHCTX_INPROC)、または現在のプロセスと同じコンピューター上の別のプロセス (MSHCTX_LOCAL) で発生する可能性があります。

*pvDestContext*<br/>
今後使用するために予約されています。0 にする必要があります。

*mshlflags*<br/>
マーシャリングするデータをクライアントプロセスに送り返すかどうかを指定します。一般的なケースでは、複数のクライアントから取得できるように、グローバルテーブルに書き込まれます。

### <a name="return-value"></a>戻り値

インターフェイスポインターが正常にマーシャリングされた S_OK。

指定されたインターフェイスはサポートされていません E_NOINTERFACE。

ストリームがいっぱいで STG_E_MEDIUMFULL。

操作が失敗した E_FAIL。

## <a name="ftmbasemarshaller_"></a><a name="marshaller"></a>FtmBase:: marshaller_

フリースレッドマーシャラーへの参照を保持します。

```cpp
Microsoft::WRL::ComPtr<IMarshal> marshaller_; ;
```

## <a name="ftmbasereleasemarshaldata"></a><a name="releasemarshaldata"></a>FtmBase:: ReleaseMarshalData

マーシャリング済みのデータパケットを破棄します。

```cpp
STDMETHODIMP ReleaseMarshalData(
   __in IStream *pStm
) override;
```

### <a name="parameters"></a>パラメーター

*pStm*<br/>
破棄するデータパケットを格納しているストリームへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="ftmbaseunmarshalinterface"></a><a name="unmarshalinterface"></a>FtmBase:: UnmarshalInterface

新しく作成されたプロキシを初期化し、そのプロキシへのインターフェイスポインターを返します。

```cpp
STDMETHODIMP UnmarshalInterface(
   __in IStream *pStm,
   __in REFIID riid,
   __deref_out void **ppv
) override;
```

### <a name="parameters"></a>パラメーター

*pStm*<br/>
インターフェイスポインターのマーシャリングを解除するストリームへのポインター。

*riid*<br/>
マーシャリング解除するインターフェイスの識別子への参照。

*ppv*<br/>
この操作が完了すると、 *riid*で要求されたインターフェイスポインターを受け取るポインター変数のアドレス。 この操作が成功した場合、**ppv*は、マーシャリングを解除するインターフェイスの要求されたインターフェイスポインターを格納します。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、E_NOINTERFACE または E_FAIL ます。
