---
title: クラスクラス
ms.date: 11/04/2016
f1_keywords:
- CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::Close
- AFXOLE/CAsyncMonikerFile::GetBinding
- AFXOLE/CAsyncMonikerFile::GetFormatEtc
- AFXOLE/CAsyncMonikerFile::Open
- AFXOLE/CAsyncMonikerFile::CreateBindStatusCallback
- AFXOLE/CAsyncMonikerFile::GetBindInfo
- AFXOLE/CAsyncMonikerFile::GetPriority
- AFXOLE/CAsyncMonikerFile::OnDataAvailable
- AFXOLE/CAsyncMonikerFile::OnLowResource
- AFXOLE/CAsyncMonikerFile::OnProgress
- AFXOLE/CAsyncMonikerFile::OnStartBinding
- AFXOLE/CAsyncMonikerFile::OnStopBinding
helpviewer_keywords:
- CAsyncMonikerFile [MFC], CAsyncMonikerFile
- CAsyncMonikerFile [MFC], Close
- CAsyncMonikerFile [MFC], GetBinding
- CAsyncMonikerFile [MFC], GetFormatEtc
- CAsyncMonikerFile [MFC], Open
- CAsyncMonikerFile [MFC], CreateBindStatusCallback
- CAsyncMonikerFile [MFC], GetBindInfo
- CAsyncMonikerFile [MFC], GetPriority
- CAsyncMonikerFile [MFC], OnDataAvailable
- CAsyncMonikerFile [MFC], OnLowResource
- CAsyncMonikerFile [MFC], OnProgress
- CAsyncMonikerFile [MFC], OnStartBinding
- CAsyncMonikerFile [MFC], OnStopBinding
ms.assetid: 17378b66-a49a-4b67-88e3-7756ad26a2fc
ms.openlocfilehash: 57ab463445f249b4e9393f19af103b7588962d5e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376992"
---
# <a name="casyncmonikerfile-class"></a>クラスクラス

ActiveX コントロール (以前の OLE コントロール) で非同期モニカーを使用するための機能が用意されています。

## <a name="syntax"></a>構文

```
class CAsyncMonikerFile : public CMonikerFile
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[同期モニカーファイル::同期モニカーファイル](#casyncmonikerfile)|`CAsyncMonikerFile` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[同期モニカーファイル::閉じる](#close)|すべてのリソースを閉じて解放します。|
|[同期モニカーファイル::バインディングを取得します。](#getbinding)|非同期転送バインディングへのポインターを取得します。|
|[ファイルを取得します。](#getformatetc)|ストリーム内のデータの形式を取得します。|
|[同期モニカーファイル::オープン](#open)|ファイルを非同期で開きます。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[ファイルを同期します。](#createbindstatuscallback)|を実装する COM オブジェクト`IBindStatusCallback`を作成します。|
|[ファイルを同期します。](#getbindinfo)|作成するバインドの種類に関する情報を要求するために、OLE システム ライブラリによって呼び出されます。|
|[同期モニカーファイル::取得優先順位](#getpriority)|OLE システム ライブラリによって呼び出され、バインディングの優先順位を取得します。|
|[同期モニカーファイル::データ利用可能](#ondataavailable)|非同期バインド操作中にクライアントが使用できるようになり、データを提供するために呼び出されます。|
|[同期モニカーファイル::オンローリソース](#onlowresource)|リソースが少ないときに呼び出されます。|
|[同期モニカーファイル::オンプログレス](#onprogress)|データのダウンロード プロセスの進行状況を示すために呼び出されます。|
|[同期モニカーファイル::オンスタートバインディング](#onstartbinding)|バインディングの開始時に呼び出されます。|
|[同期モニカーファイル::オンストップバインディング](#onstopbinding)|非同期転送が停止したときに呼び出されます。|

## <a name="remarks"></a>解説

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)から派生し、次に[COleStreamFile](../../mfc/reference/colestreamfile-class.md)から`CAsyncMonikerFile`派生し[、IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker)インターフェイスを使用して、URL から非同期にファイルを読み込むなど、任意のデータ ストリームに非同期的にアクセスします。 ファイルは、ActiveX コントロールのデータパス プロパティにすることができます。

非同期モニカーは、主にインターネット対応アプリケーションおよび ActiveX コントロールで使用され、ファイル転送中に応答性の高いユーザー インターフェイスを提供します。 この主要な例は[、CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)を使用して ActiveX コントロールに非同期プロパティを提供することです。 オブジェクト`CDataPathProperty`は、長いプロパティ交換プロセス中に新しいデータが利用可能であることを示すコールバックを繰り返し取得します。

インターネット アプリケーションで非同期モニカーと ActiveX コントロールを使用する方法の詳細については、次の記事を参照してください。

- [インターネットの最初のステップ: 非同期モニカー](../../mfc/asynchronous-monikers-on-the-internet.md)

- [インターネットの最初の手順: ActiveX コントロール](../../mfc/activex-controls-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

`CAsyncMonikerFile`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

## <a name="casyncmonikerfilecasyncmonikerfile"></a><a name="casyncmonikerfile"></a>同期モニカーファイル::同期モニカーファイル

`CAsyncMonikerFile` オブジェクトを構築します。

```
CAsyncMonikerFile();
```

### <a name="remarks"></a>解説

`IBindHost`インターフェイスは作成されません。 `IBindHost`は、メンバー関数に指定した場合にのみ`Open`使用されます。

`IBindHost`インターフェイスの詳細については、Windows SDK を参照してください。

## <a name="casyncmonikerfileclose"></a><a name="close"></a>同期モニカーファイル::閉じる

すべてのリソースを閉じて解放するには、この関数を呼び出します。

```
virtual void Close();
```

### <a name="remarks"></a>解説

開いていないファイルまたは既に閉じているファイルに対して呼び出すことができます。

## <a name="casyncmonikerfilecreatebindstatuscallback"></a><a name="createbindstatuscallback"></a>ファイルを同期します。

を実装する COM オブジェクト`IBindStatusCallback`を作成します。

```
virtual IUnknown* CreateBindStatusCallback(IUnknown* pUnkControlling);
```

### <a name="parameters"></a>パラメーター

*pUnk制御*<br/>
制御対象不明 (外部`IUnknown`) へのポインターまたは NULL (集約が使用されていない場合)。

### <a name="return-value"></a>戻り値

*pUnkControlling*が NULL でない場合、関数は、サポートしている`IUnknown``IBindStatusCallback`新しい COM オブジェクトの内部へのポインターを返します。 NULL`pUnkControlling`の場合、関数はをサポート`IUnknown``IBindStatusCallback`する新しい COM オブジェクトの を指すポインターを返します。

### <a name="remarks"></a>解説

`CAsyncMonikerFile`を実装する COM オブジェクト`IBindStatusCallback`が必要です。 MFC は、このようなオブジェクトを実装し、集計可能です。 オーバーライド`CreateBindStatusCallback`して、独自の COM オブジェクトを返すことができます。 COM オブジェクトは、COM オブジェクトの不明な`CreateBindStatusCallback`制御を呼び出すことによって、MFC の実装を集約できます。 COM サポートを`CCmdTarget`使用して実装された COM オブジェクトは、`CCmdTarget::GetControllingUnknown`を使用して未知の制御を取得できます。

または、COM オブジェクトを呼び出`CreateBindStatusCallback( NULL )`すことによって MFC の実装にデリゲートできます。

呼び出し`CreateBindStatusCallback`[を開きます](#open)。

非同期モニカーと非同期バインディングの詳細については、 [IBindStatusCallback](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775060\(v=vs.85\))インターフェイスと[非同期バインディングとストレージのしくみ](/windows/win32/Stg/how-asynchronous-binding-and-storage-work)を参照してください。 集計の詳細については、「[集計](/windows/win32/com/aggregation)」を参照してください。 3 つのトピックはすべて Windows SDK に含まれています。

## <a name="casyncmonikerfilegetbindinfo"></a><a name="getbindinfo"></a>ファイルを同期します。

非同期モニカーのクライアントから呼び出され、バインドする方法を非同期モニカーに伝えます。

```
virtual DWORD GetBindInfo() const;
```

### <a name="return-value"></a>戻り値

の設定を取得します`IBindStatusCallBack`。 `IBindStatusCallback`インターフェイスの詳細については、Windows SDK を参照してください。

### <a name="remarks"></a>解説

既定の実装では、バインディングを非同期に設定し、ストレージ メディア (ストリーム) を使用し、データ プッシュ モデルを使用するように設定します。 バインディングの動作を変更する場合は、この関数をオーバーライドします。

これを行う理由の 1 つは、データ プッシュ モデルではなくデータ プル モデルを使用してバインドすることです。 データプルモデルでは、クライアントがバインド操作を実行し、モニカーは読み取り時にのみクライアントにデータを提供します。 データ プッシュ モデルでは、モニカーは非同期バインド操作を実行し、新しいデータが使用可能になったときにクライアントに継続的に通知します。

## <a name="casyncmonikerfilegetbinding"></a><a name="getbinding"></a>同期モニカーファイル::バインディングを取得します。

非同期転送バインディングへのポインターを取得します。

```
IBinding* GetBinding() const;
```

### <a name="return-value"></a>戻り値

非同期転送の開始`IBinding`時に提供されるインターフェイスへのポインター。 何らかの理由で転送を非同期に行うことができない場合は NULL を返します。

### <a name="remarks"></a>解説

これにより、`IBinding`インタフェース`IBinding::Abort`を通じてデータ転送プロセス`IBinding::Pause`を制御できます。 `IBinding::Resume`

`IBinding`インターフェイスの詳細については、Windows SDK を参照してください。

## <a name="casyncmonikerfilegetformatetc"></a><a name="getformatetc"></a>ファイルを取得します。

ストリーム内のデータの形式を取得します。

```
FORMATETC* GetFormatEtc() const;
```

### <a name="return-value"></a>戻り値

現在開かれているストリームの Windows 構造体[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)へのポインター。 モニカーがバインドされていない場合、非同期でない場合、または非同期操作が開始されていない場合は NULL を返します。

## <a name="casyncmonikerfilegetpriority"></a><a name="getpriority"></a>同期モニカーファイル::取得優先順位

バインディング プロセスがバインディング操作のスレッドに与えられた優先順位を受け取り始めると、非同期モニカーのクライアントから呼び出されます。

```
virtual LONG GetPriority() const;
```

### <a name="return-value"></a>戻り値

非同期転送が行われる優先順位。 標準スレッド優先順位フラグの 1 つ:THREAD_PRIORITY_ABOVE_NORMAL、THREAD_PRIORITY_BELOW_NORMAL、THREAD_PRIORITY_HIGHEST、THREAD_PRIORITY_IDLE、THREAD_PRIORITY_LOWEST、THREAD_PRIORITY_NORMAL、およびTHREAD_PRIORITY_TIME_CRITICAL。 これらの値の説明については、Windows 関数[SetThreadPriority](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority)を参照してください。

### <a name="remarks"></a>解説

`GetPriority`直接呼び出さないでください。 THREAD_PRIORITY_NORMALは、既定の実装によって返されます。

## <a name="casyncmonikerfileondataavailable"></a><a name="ondataavailable"></a>同期モニカーファイル::データ利用可能

非同期モニカーは、非同期`OnDataAvailable`バインド操作中に、使用可能になったときにクライアントにデータを提供する呼び出しです。

```
virtual void OnDataAvailable(DWORD dwSize, DWORD bscfFlag);
```

### <a name="parameters"></a>パラメーター

*Dwsize*<br/>
バインドの開始以降に使用可能なデータの累積量 (バイト単位)。 データ量が操作に関連しないか、または特定の量が使用可能でないことを示すゼロを指定できます。

*フラグ*<br/>
BSCF 列挙値。 次の値の 1 つ以上を指定できます。

- BSCF_FIRSTDATANOTIFICATION特定のバインド操作に対`OnDataAvailable`する最初の呼び出しを識別します。

- BSCF_INTERMEDIATEDATANOTIFICATION バインド操作の仲介呼び出`OnDataAvailable`しを識別します。

- BSCF_LASTDATANOTIFICATION バインド操作の最後の`OnDataAvailable`呼び出しを識別します。

### <a name="remarks"></a>解説

この関数の既定の実装は、何も行いません。 実装例については、次の例を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWinInet#5](../../mfc/codesnippet/cpp/casyncmonikerfile-class_1.cpp)]

## <a name="casyncmonikerfileonlowresource"></a><a name="onlowresource"></a>同期モニカーファイル::オンローリソース

リソースが少ない場合にモニカーによって呼び出されます。

```
virtual void OnLowResource();
```

### <a name="remarks"></a>解説

既定の実装では`GetBinding( )-> Abort( )`、 が呼び出されます。

## <a name="casyncmonikerfileonprogress"></a><a name="onprogress"></a>同期モニカーファイル::オンプログレス

このバインド操作の現在の進行状況を示すために、モニカーによって繰り返し呼び出されます。

```
virtual void OnProgress(
    ULONG ulProgress,
    ULONG ulProgressMax,
    ULONG ulStatusCode,
    LPCTSTR szStatusText);
```

### <a name="parameters"></a>パラメーター

*ウルプログレス*<br/>
*ulProgressMax*で指定された予想される最大値に対するバインド操作の現在の進行状況を示します。

*ウルプログレスマックス*<br/>
この操作の呼び出しの間の*ulProgress* `OnProgress`の期待される最大値を示します。

*州の状況コード*<br/>
バインド操作の進行状況に関する追加情報を提供します。 有効な値は列挙体`BINDSTATUS`から取得されます。 可能な値については、「解説」を参照してください。

*テキスト*<br/>
*ulStatusCode*の値に応じて、現在の進行状況に関する情報。 可能な値については、「解説」を参照してください。

### <a name="remarks"></a>解説

*ulStatusCode* (および各値の*szStatusText)* に指定できる値は次のとおりです。

|||
|-|-|
|BINDSTATUS_FINDINGRESOURCE  |バインド操作は、バインドされているオブジェクトまたはストレージを保持するリソースを検索します。 *szStatusText*は、検索対象のリソースの表示名を提供します ("www.microsoft.com" など)。  |
|BINDSTATUS_CONNECTING  |バインド操作は、バインドされているオブジェクトまたはストレージを保持しているリソースに接続しています。 *szStatusText*は、接続されているリソースの表示名 (IP アドレスなど) を提供します。  |
|BINDSTATUS_SENDINGREQUEST|バインド操作は、バインドされているオブジェクトまたはストレージを要求しています。 *szStatusText*は、オブジェクトの表示名 (ファイル名など) を提供します。|
|BINDSTATUS_REDIRECTING  |バインド操作が別のデータの場所にリダイレクトされました。 *新*しいデータの場所の表示名を提供します。  |
|BINDSTATUS_USINGCACHEDCOPY  |バインド操作は、キャッシュされたコピーから要求されたオブジェクトまたはストレージを取得しています。 *テキストは*NULL です。  |
|BINDSTATUS_BEGINDOWNLOADDATA  |バインド操作が、バインドされているオブジェクトまたはストレージの受信を開始しました。 *szStatusText は*、データの場所の表示名を提供します。|
|BINDSTATUS_DOWNLOADINGDATA  |バインド操作は、バインドされているオブジェクトまたはストレージを引き続き受け取ります。 *szStatusText は*、データの場所の表示名を提供します。  |
|BINDSTATUS_ENDDOWNLOADDATA  |バインド操作は、バインドされているオブジェクトまたはストレージの受信を終了しました。 *szStatusText は*、データの場所の表示名を提供します。  |
|BINDSTATUS_CLASSIDAVAILABLE  |バインドされているオブジェクトのインスタンスが作成されようとしています。 *szStatusText*は、新しいオブジェクトの CLSID を文字列形式で提供するため、必要に応じて、クライアントはバインド操作をキャンセルできます。  |

## <a name="casyncmonikerfileonstartbinding"></a><a name="onstartbinding"></a>同期モニカーファイル::オンスタートバインディング

バインドの開始時にアクションを実行するには、派生クラスでこの関数をオーバーライドします。

```
virtual void OnStartBinding();
```

### <a name="remarks"></a>解説

この関数はモニカーによって呼び戻されます。 既定の実装では、何も行われません。

## <a name="casyncmonikerfileonstopbinding"></a><a name="onstopbinding"></a>同期モニカーファイル::オンストップバインディング

バインド操作の終了時にモニカーによって呼び出されます。

```
virtual void OnStopBinding(HRESULT hresult, LPCTSTR szError);
```

### <a name="parameters"></a>パラメーター

*Hresult*<br/>
エラーまたは警告の値である HRESULT。

*エラー*<br/>
エラーを説明する文字列。

### <a name="remarks"></a>解説

転送が停止したときにアクションを実行するには、この関数をオーバーライドします。 既定では、関数は`IBinding`をリリースします。

`IBinding`インターフェイスの詳細については、Windows SDK を参照してください。

## <a name="casyncmonikerfileopen"></a><a name="open"></a>同期モニカーファイル::オープン

ファイルを非同期で開くには、このメンバー関数を呼び出します。

```
virtual BOOL Open(
    LPCTSTR lpszURL,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszURL,
    IBindHost* pBindHost,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    IBindHost* pBindHost,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszURL,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszURL,
    IUnknown* pUnknown,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    IUnknown* pUnknown,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>パラメーター

*を指定します。*<br/>
非同期に開くファイルへのポインター。 ファイルには、任意の有効な URL またはファイル名を指定できます。

*pError*<br/>
ファイルの例外へのポインター。 エラーが発生した場合は、その原因に設定されます。

*pモニカー*<br/>
で取得`IOleClientSite::GetMoniker(OLEWHICHMK_CONTAINER)`できるドキュメント独自のモニカーと`IMoniker`、パス名から作成されたモニカーの組み合わせである、非同期モニカー インターフェイスへのポインター。 コントロールはバインドにこのモニカーを使用できますが、これはコントロールが保存するモニカーではありません。

*ホスト*<br/>
相対パス名の`IBindHost`可能性があるモニカーを作成するために使用されるインターフェイスへのポインター。 バインド ホストが無効であるかモニカーを提供しない場合、呼び出しは既定で`Open(lpszFileName,pError)`に. `IBindHost`インターフェイスの詳細については、Windows SDK を参照してください。

*サービスプロバイダ*<br/>
`IServiceProvider` インターフェイスへのポインター。 サービス プロバイダが無効であるか、 の`IBindHost`サービスを提供できない場合、呼び出し`Open(lpszFileName,pError)`は既定で に設定されます。

*pUnknown*<br/>
`IUnknown` インターフェイスへのポインター。 見`IServiceProvider`つかった場合、関数は に対`IBindHost`してクエリを実行します。 サービス プロバイダが無効であるか、 の`IBindHost`サービスを提供できない場合、呼び出し`Open(lpszFileName,pError)`は既定で に設定されます。

### <a name="return-value"></a>戻り値

ファイルが正常に開かれた場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

この呼び出しは、バインディング プロセスを開始します。

*lpszURL*パラメータには、URL またはファイル名を使用できます。 次に例を示します。

[!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/casyncmonikerfile-class_2.cpp)]

\- または

[!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/casyncmonikerfile-class_3.cpp)]

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/cmonikerfile-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/cmonikerfile-class.md)<br/>
[クラス](../../mfc/reference/cdatapathproperty-class.md)
