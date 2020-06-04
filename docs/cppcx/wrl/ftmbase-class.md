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
ms.openlocfilehash: d37cdddda8cf8894016ed80b9055fe106b1600f7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371514"
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

詳細については、「[ランタイム クラス クラス](runtimeclass-class.md)」を参照してください。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

| 名前                         | 説明                                        |
| ---------------------------- | -------------------------------------------------- |
| [フォートムベース::フォートムベース](#ftmbase) | `FtmBase` クラスの新しいインスタンスを初期化します。 |

### <a name="public-methods"></a>パブリック メソッド

| 名前                                                               | 説明                                                                                                                                                          |
| ------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [を使用します。](#createglobalinterfacetable) | グローバル インターフェイス テーブル (GIT) を作成します。                                                                                                                              |
| [フトムベース::Dコネクトオブジェクト](#disconnectobject)                     | オブジェクトへのすべての外部接続を強制的に解放します。 オブジェクトのサーバーは、シャットダウンする前に、このメソッドのオブジェクトの実装を呼び出します。                |
| [フトムベース::ゲットマーシャルサイズマックス](#getmarshalsizemax)                   | 指定したオブジェクトで指定したインターフェイス ポインターをマーシャリングするために必要なバイト数の上限を取得します。                                                |
| [フトムベース::ゲットアンマーシャルクラス](#getunmarshalclass)                   | COM が対応するプロキシのコードを含む DLL を検索するために使用する CLSID を取得します。 COM は、プロキシの初期化されていないインスタンスを作成するために、この DLL を読み込みます。 |
| [フォートムベース::マーシャルインターフェイス](#marshalinterface)                     | クライアント プロセスでプロキシ オブジェクトを初期化するために必要なデータをストリームに書き込みます。                                                                          |
| [フトムベース::リリースマーシャルデータ](#releasemarshaldata)                 | マーシャリングされたデータ パケットを破棄します。                                                                                                                                    |
| [フトムベース::アンマーシャルインターフェイス](#unmarshalinterface)                 | 新しく作成されたプロキシを初期化し、そのプロキシへのインターフェイス ポインターを返します。                                                                                    |

### <a name="public-data-members"></a>パブリック データ メンバー

| 名前                                | 説明                                       |
| ----------------------------------- | ------------------------------------------------- |
| [フトムベース::marshaller_](#marshaller) | フリー スレッド マーシャラーへの参照を保持します。 |

## <a name="inheritance-hierarchy"></a>継承階層

`FtmBase`

## <a name="requirements"></a>必要条件

**ヘッダー:** ftm.h

**名前空間:** Microsoft::WRL

## <a name="ftmbasecreateglobalinterfacetable"></a><a name="createglobalinterfacetable"></a>を使用します。

グローバル インターフェイス テーブル (GIT) を作成します。

```cpp
static HRESULT CreateGlobalInterfaceTable(
   __out IGlobalInterfaceTable **git
);
```

### <a name="parameters"></a>パラメーター

*Git*<br/>
この操作が完了すると、グローバル インターフェイス テーブルへのポインタ。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

### <a name="remarks"></a>解説

詳細については、MSDN ライブラリ`IGlobalInterfaceTable`の`COM Reference`トピックの`COM Interfaces`サブトピックのトピックを参照してください。

## <a name="ftmbasedisconnectobject"></a><a name="disconnectobject"></a>フトムベース::Dコネクトオブジェクト

オブジェクトへのすべての外部接続を強制的に解放します。 オブジェクトのサーバーは、シャットダウンする前に、このメソッドのオブジェクトの実装を呼び出します。

```cpp
STDMETHODIMP DisconnectObject(
   __in DWORD dwReserved
) override;
```

### <a name="parameters"></a>パラメーター

*dw予約済み*<br/>
今後使用するために予約されています。0 にする必要があります。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="ftmbaseftmbase"></a><a name="ftmbase"></a>フォートムベース::フォートムベース

`FtmBase` クラスの新しいインスタンスを初期化します。

```cpp
FtmBase();
```

## <a name="ftmbasegetmarshalsizemax"></a><a name="getmarshalsizemax"></a>フトムベース::ゲットマーシャルサイズマックス

指定したオブジェクトで指定したインターフェイス ポインターをマーシャリングするために必要なバイト数の上限を取得します。

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
マーシャリングするインターフェイス ポインタ。NULL を指定できます。

*コンテキスト*<br/>
指定したインターフェイスをマーシャリング解除する宛先コンテキスト。

1 つ以上の MSHCTX 列挙値を指定します。

現在、マーシャリング解除は、現在のプロセスの別のアパートメント (MSHCTX_INPROC) または現在のプロセス (MSHCTX_LOCAL) と同じコンピュータ上の別のプロセスで発生する可能性があります。

*コンテキスト*<br/>
将来の使用のために予約されています。NULL である必要があります。

*mshlflags*<br/>
マーシャリングするデータをクライアント プロセス (一般的なケース) に転送するか、グローバル テーブルに書き込むかを示すフラグです。 1 つ以上の MSHLFLAGS 列挙値を指定します。

*Psize*<br/>
この操作が完了すると、マーシャリング ストリームに書き込まれるデータ量の上限へのポインター。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合は、E_FAILまたはE_NOINTERFACE。

## <a name="ftmbasegetunmarshalclass"></a><a name="getunmarshalclass"></a>フトムベース::ゲットアンマーシャルクラス

COM が対応するプロキシのコードを含む DLL を検索するために使用する CLSID を取得します。 COM は、プロキシの初期化されていないインスタンスを作成するために、この DLL を読み込みます。

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
マーシャリングするインターフェイスへのポインター。呼び出し元が目的のインターフェイスへのポインターを持っていない場合は NULL を指定できます。

*コンテキスト*<br/>
指定したインターフェイスをマーシャリング解除する宛先コンテキスト。

1 つ以上の MSHCTX 列挙値を指定します。

マーシャリング解除は、現在のプロセスの別のアパートメント (MSHCTX_INPROC) で発生するか、現在のプロセス (MSHCTX_LOCAL) と同じコンピュータ上の別のプロセスで発生する可能性があります。

*コンテキスト*<br/>
将来の使用のために予約されています。NULL である必要があります。

*mshlflags*<br/>
この操作が完了したら、クライアント プロセスでプロキシを作成するために使用される CLSID へのポインター。

*pCid*

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合は、S_FALSE。

## <a name="ftmbasemarshalinterface"></a><a name="marshalinterface"></a>フォートムベース::マーシャルインターフェイス

クライアント プロセスでプロキシ オブジェクトを初期化するために必要なデータをストリームに書き込みます。

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
マーシャリングするインターフェイス ポインターへのポインター。呼び出し元が目的のインターフェイスへのポインターを持っていない場合は NULL を指定できます。

*コンテキスト*<br/>
指定したインターフェイスをマーシャリング解除する宛先コンテキスト。

1 つ以上の MSHCTX 列挙値を指定します。

マーシャリング解除は、現在のプロセスの別のアパートメント (MSHCTX_INPROC) または現在のプロセスと同じコンピュータ上の別のプロセス (MSHCTX_LOCAL) で発生する可能性があります。

*コンテキスト*<br/>
今後使用するために予約されています。0 にする必要があります。

*mshlflags*<br/>
マーシャリングするデータをクライアント プロセス (一般的なケース) に転送するか、グローバル テーブルに書き込むかを指定します。

### <a name="return-value"></a>戻り値

S_OK インターフェイス ポインターが正常にマーシャリングされました。

E_NOINTERFACE 指定されたインターフェイスはサポートされていません。

STG_E_MEDIUMFULL ストリームがいっぱいです。

E_FAIL 操作に失敗しました。

## <a name="ftmbasemarshaller_"></a><a name="marshaller"></a>フトムベース::marshaller_

フリー スレッド マーシャラーへの参照を保持します。

```cpp
Microsoft::WRL::ComPtr<IMarshal> marshaller_; ;
```

## <a name="ftmbasereleasemarshaldata"></a><a name="releasemarshaldata"></a>フトムベース::リリースマーシャルデータ

マーシャリングされたデータ パケットを破棄します。

```cpp
STDMETHODIMP ReleaseMarshalData(
   __in IStream *pStm
) override;
```

### <a name="parameters"></a>パラメーター

*pStm*<br/>
破棄されるデータ パケットを含むストリームへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="ftmbaseunmarshalinterface"></a><a name="unmarshalinterface"></a>フトムベース::アンマーシャルインターフェイス

新しく作成されたプロキシを初期化し、そのプロキシへのインターフェイス ポインターを返します。

```cpp
STDMETHODIMP UnmarshalInterface(
   __in IStream *pStm,
   __in REFIID riid,
   __deref_out void **ppv
) override;
```

### <a name="parameters"></a>パラメーター

*pStm*<br/>
インターフェイス ポインターのマーシャリング解除元のストリームへのポインター。

*riid*<br/>
マーシャリング解除するインターフェイスの識別子への参照。

*Ppv*<br/>
この操作が完了すると *、riid*で要求されたインターフェイス ポインターを受け取るポインター変数のアドレス。 この操作が成功した場合、**ppv*にはマーシャリング解除するインターフェイスの要求されたインターフェイス ポインタが含まれます。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合は、E_NOINTERFACEまたはE_FAIL。
