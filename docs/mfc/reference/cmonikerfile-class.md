---
description: '詳細情報: CMonikerFile クラス'
title: CMonikerFile クラス
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
ms.openlocfilehash: d59de05f688c10d3dbfa6682777d5fd11d4f53ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331582"
---
# <a name="cmonikerfile-class"></a>CMonikerFile クラス

[IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker)によって名前が付けられたデータのストリーム ( [IStream](/windows/win32/api/objidl/nn-objidl-istream)) を表します。

## <a name="syntax"></a>構文

```
class CMonikerFile : public COleStreamFile
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMonikerFile::CMonikerFile](#cmonikerfile)|`CMonikerFile` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMonikerFile:: Close](#close)|ストリームをデタッチして解放し、モニカーを解放します。|
|[CMonikerFile::D etach](#detach)|`IMoniker`このオブジェクトからをデタッチし `CMonikerFile` ます。|
|[CMonikerFile:: GetMoniker](#getmoniker)|現在のモニカーを返します。|
|[CMonikerFile:: Open](#open)|指定されたファイルを開いてストリームを取得します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CMonikerFile:: CreateBindContext](#createbindcontext)|バインドコンテキストを取得するか、既定の初期化済みバインドコンテキストを作成します。|

## <a name="remarks"></a>解説

モニカーには、ファイルのパス名のような情報が含まれています。 モニカーオブジェクトのインターフェイスへのポインターがある場合は、 `IMoniker` ファイルが実際に置かれている場所に関するその他の特定の情報がなくても、識別されたファイルにアクセスできます。

から派生した `COleStreamFile` `CMonikerFile` モニカーまたは文字列形式をモニカーとして受け取り、モニカーが名前であるストリームにバインドします。 その後、そのストリームに対して読み取りと書き込みを行うことができます。 の実際の目的は、に `CMonikerFile` よって名前が付けられたに簡単にアクセスできるようにすることです。これにより、ストリームに `IStream` バインドする `IMoniker` 必要がなく、 `CFile` ストリームに対する機能を持つことができます。

`CMonikerFile` は、ストリーム以外にバインドするためには使用できません。 ストレージまたはオブジェクトにバインドする場合は、インターフェイスを直接使用する必要があり `IMoniker` ます。

ストリームとモニカーの詳細については、「 [COleStreamFile](../../mfc/reference/colestreamfile-class.md) In The *MFC Reference* 」および「 [IStream](/windows/win32/api/objidl/nn-objidl-istream) and [IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker) in the Windows SDK」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

`CMonikerFile`

## <a name="requirements"></a>要件

**ヘッダー:** afxole

## <a name="cmonikerfileclose"></a><a name="close"></a> CMonikerFile:: Close

ストリームをデタッチおよび解放し、モニカーを解放するには、この関数を呼び出します。

```
virtual void Close();
```

### <a name="remarks"></a>解説

開かれていないストリームまたは既に閉じられているストリームで呼び出すことができます。

## <a name="cmonikerfilecmonikerfile"></a><a name="cmonikerfile"></a> CMonikerFile::CMonikerFile

`CMonikerFile` オブジェクトを構築します。

```
CMonikerFile();
```

## <a name="cmonikerfilecreatebindcontext"></a><a name="createbindcontext"></a> CMonikerFile:: CreateBindContext

既定の初期化済みバインドコンテキストを作成するには、この関数を呼び出します。

```
IBindCtx* CreateBindContext(CFileException* pError);
```

### <a name="parameters"></a>パラメーター

*pError*<br/>
ファイル例外へのポインター。 エラーが発生した場合は、その原因がに設定されます。

### <a name="return-value"></a>戻り値

成功した場合にバインドする [IBindCtx](/windows/win32/api/objidl/nn-objidl-ibindctx) のバインドコンテキストへのポインター。それ以外の場合は NULL。 インスタンスがインターフェイスを使用して開かれている場合 `IBindHost` 、バインドコンテキストはから取得され `IBindHost` ます。 インターフェイスが存在しない場合、 `IBindHost` またはインターフェイスがバインドコンテキストを返すことができない場合は、バインドコンテキストが作成されます。 [IBindHost](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775076\(v=vs.85\))インターフェイスの説明については、Windows SDK を参照してください。

### <a name="remarks"></a>解説

バインドコンテキストは、特定のモニカーバインディング操作に関する情報を格納するオブジェクトです。 この関数をオーバーライドして、カスタムバインドコンテキストを提供できます。

## <a name="cmonikerfiledetach"></a><a name="detach"></a> CMonikerFile::D etach

ストリームを閉じるには、この関数を呼び出します。

```
BOOL Detach(CFileException* pError = NULL);
```

### <a name="parameters"></a>パラメーター

*pError*<br/>
ファイル例外へのポインター。 エラーが発生した場合は、その原因がに設定されます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

## <a name="cmonikerfilegetmoniker"></a><a name="getmoniker"></a> CMonikerFile:: GetMoniker

現在のモニカーへのポインターを取得するには、この関数を呼び出します。

```
IMoniker* GetMoniker() const;
```

### <a name="return-value"></a>戻り値

現在のモニカーインターフェイス ( [IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker)) へのポインター。

### <a name="remarks"></a>解説

`CMonikerFile`はインターフェイスではないため、返されるポインターは、( [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)を通じて) 参照カウントをインクリメントしません。また、オブジェクトが解放されるとモニカーが解放され `CMonikerFile` ます。 モニカーを保持する場合、または自分でモニカーをリリースする場合は、それが必要 `AddRef` です。

## <a name="cmonikerfileopen"></a><a name="open"></a> CMonikerFile:: Open

ファイルまたはモニカーオブジェクトを開くには、このメンバー関数を呼び出します。

```
virtual BOOL Open(
    LPCTSTR lpszURL,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>パラメーター

*lpszURL*<br/>
開くファイルの URL またはファイル名。

*pError*<br/>
ファイル例外へのポインター。 エラーが発生した場合は、その原因がに設定されます。

*pMoniker*<br/>
`IMoniker`ストリームを取得するために使用されるモニカーインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

*Lpszurl* パラメーターは、Macintosh では使用できません。 の *Pmoniker* 形式のみを `Open` Macintosh で使用できます。

*Lpszurl* パラメーターには、url またはファイル名を使用できます。 次に例を示します。

[!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/cmonikerfile-class_1.cpp)]

\- または

[!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/cmonikerfile-class_2.cpp)]

## <a name="see-also"></a>関連項目

[COleStreamFile クラス](../../mfc/reference/colestreamfile-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CAsyncMonikerFile クラス](../../mfc/reference/casyncmonikerfile-class.md)
