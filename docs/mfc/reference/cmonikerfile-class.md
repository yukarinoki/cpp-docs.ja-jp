---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CMonikerFile
- AFXOLE/CMonikerFile
- AFXOLE/CMonikerFile::CMonikerFile
- AFXOLE/CMonikerFile::Close
- AFXOLE/CMonikerFile::Detach
- AFXOLE/CMonikerFile::GetMoniker
- AFXOLE/CMonikerFile::Open
- AFXOLE/CMonikerFile::CreateBindContext
helpviewer_keywords:
- CMonikerFile [MFC], CMonikerFile
- CMonikerFile [MFC], Close
- CMonikerFile [MFC], Detach
- CMonikerFile [MFC], GetMoniker
- CMonikerFile [MFC], Open
- CMonikerFile [MFC], CreateBindContext
ms.assetid: 87be5966-f4f7-4235-bce2-1fa39e9417de
ms.openlocfilehash: fc74ad2499fcde63faa2c5859a87fd9ffd2846eb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319782"
---
# <a name="cmonikerfile-class"></a>クラス

[IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker)によって指定されたデータストリーム ( [IStream](/windows/win32/api/objidl/nn-objidl-istream)) を表します。

## <a name="syntax"></a>構文

```
class CMonikerFile : public COleStreamFile
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cモニカーファイル::Cモニカーファイル](#cmonikerfile)|`CMonikerFile` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ファイル::閉じる](#close)|ストリームをデタッチして解放し、モニカーを解放します。|
|[クモニカーファイル::Dエタッハ](#detach)|この`CMonikerFile`オブジェクトから`IMoniker`をデタッチします。|
|[クモニカファイル::ゲットモニカー](#getmoniker)|現在のモニカーを返します。|
|[ファイル::オープン](#open)|ストリームを取得するために指定されたファイルを開きます。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[ファイル::バインドコンテキストを作成します。](#createbindcontext)|バインド コンテキストを取得するか、既定の初期化済みバインド コンテキストを作成します。|

## <a name="remarks"></a>解説

モニカーには、ファイルへのパス名のような情報が含まれています。 モニカー オブジェクトのインターフェイスへのポインターがある場合は、ファイル`IMoniker`が実際に配置されている場所に関する他の特定の情報を持たずに、識別されたファイルにアクセスできます。

から`COleStreamFile`派生した`CMonikerFile`モニカーまたは文字列表現をモニカーに取り込み、モニカーが名前であるストリームにバインドします。 その後、そのストリームに対する読み取りと書き込みを行うことができます。 本当の`CMonikerFile`目的は、ストリームにバインドする必要`IStream`がな、`IMoniker`ストリームへの機能を持つ`CFile`必要がないように、sで名前付けされたsへの簡単なアクセスを提供することです。

`CMonikerFile`ストリーム以外にバインドするために使用することはできません。 ストレージまたはオブジェクトにバインドする場合は、インターフェースを`IMoniker`直接使用する必要があります。

ストリームとモニカーの詳細については *、MFC リファレンス*の[COleStreamFile](../../mfc/reference/colestreamfile-class.md)および Windows SDK の[IStream](/windows/win32/api/objidl/nn-objidl-istream)と[IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

`CMonikerFile`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

## <a name="cmonikerfileclose"></a><a name="close"></a>ファイル::閉じる

ストリームをデタッチして解放し、モニカーを解放します。

```
virtual void Close();
```

### <a name="remarks"></a>解説

開かれないストリームまたは既に閉じているストリームで呼び出すことができます。

## <a name="cmonikerfilecmonikerfile"></a><a name="cmonikerfile"></a>Cモニカーファイル::Cモニカーファイル

`CMonikerFile` オブジェクトを構築します。

```
CMonikerFile();
```

## <a name="cmonikerfilecreatebindcontext"></a><a name="createbindcontext"></a>ファイル::バインドコンテキストを作成します。

既定の初期化されたバインド コンテキストを作成します。

```
IBindCtx* CreateBindContext(CFileException* pError);
```

### <a name="parameters"></a>パラメーター

*pError*<br/>
ファイル例外へのポインター。 エラーが発生した場合は、その原因に設定されます。

### <a name="return-value"></a>戻り値

成功した場合にバインドするバインド コンテキスト[IBindCtx](/windows/win32/api/objidl/nn-objidl-ibindctx)へのポインター。それ以外の場合は NULL。 `IBindHost`インスタンスがインターフェイスで開かれた場合、バインド コンテキストは`IBindHost`から取得されます。 インターフェイスがない`IBindHost`場合、またはインターフェイスがバインド コンテキストを返さない場合は、バインド コンテキストが作成されます。 [インターフェイス](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775076\(v=vs.85\))の詳細については、Windows SDK を参照してください。

### <a name="remarks"></a>解説

バインド コンテキストは、特定のモニカー バインド操作に関する情報を格納するオブジェクトです。 この関数をオーバーライドして、カスタム バインド コンテキストを提供できます。

## <a name="cmonikerfiledetach"></a><a name="detach"></a>クモニカーファイル::Dエタッハ

ストリームを閉じます。

```
BOOL Detach(CFileException* pError = NULL);
```

### <a name="parameters"></a>パラメーター

*pError*<br/>
ファイル例外へのポインター。 エラーが発生した場合は、その原因に設定されます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

## <a name="cmonikerfilegetmoniker"></a><a name="getmoniker"></a>クモニカファイル::ゲットモニカー

現在のモニカーへのポインターを取得します。

```
IMoniker* GetMoniker() const;
```

### <a name="return-value"></a>戻り値

現在のモニカー インターフェイス ( [IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker)) へのポインター。

### <a name="remarks"></a>解説

インターフェイス`CMonikerFile`ではないため、返されるポインターは参照カウントをインクリメントしません[(AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)を使用して) オブジェクトが解放されると`CMonikerFile`モニカーが解放されます。 モニカーにしがみついたり、自分で解放したりしたい場合は、それを`AddRef`解除する必要があります。

## <a name="cmonikerfileopen"></a><a name="open"></a>ファイル::オープン

ファイルまたはモニカー オブジェクトを開く場合は、このメンバー関数を呼び出します。

```
virtual BOOL Open(
    LPCTSTR lpszURL,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>パラメーター

*を指定します。*<br/>
開くファイルの URL またはファイル名。

*pError*<br/>
ファイル例外へのポインター。 エラーが発生した場合は、その原因に設定されます。

*pモニカー*<br/>
ストリームを取得するために使用されるモニカー`IMoniker`インターフェイスへのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

*lpszURL*パラメータは、Macintosh では使用できません。 マッキントッシュでは*pMoniker*形式のみ使用`Open`できます。

*lpszURL*パラメータには、URL またはファイル名を使用できます。 次に例を示します。

[!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/cmonikerfile-class_1.cpp)]

\- または

[!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/cmonikerfile-class_2.cpp)]

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/colestreamfile-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラスクラス](../../mfc/reference/casyncmonikerfile-class.md)
