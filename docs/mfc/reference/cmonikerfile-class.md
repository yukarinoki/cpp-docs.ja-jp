---
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
ms.openlocfilehash: 7fb0ad3eef781be1b5ca358e825c09a88c0109e3
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503819"
---
# <a name="cmonikerfile-class"></a>CMonikerFile クラス

データのストリームを表します ( [IStream](/windows/desktop/api/objidl/nn-objidl-istream)) によってという名前を[IMoniker](/windows/desktop/api/objidl/nn-objidl-imoniker)します。

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
|[CMonikerFile::Close](#close)|デタッチし、ストリームを解放し、モニカーを解放します。|
|[CMonikerFile::Detach](#detach)|デタッチ、`IMoniker`これから`CMonikerFile`オブジェクト。|
|[CMonikerFile::GetMoniker](#getmoniker)|現在のモニカーを返します。|
|[CMonikerFile::Open](#open)|ストリームを取得する指定されたファイルを開きます。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CMonikerFile::CreateBindContext](#createbindcontext)|バインド コンテキストを取得するか、既定値に初期化のバインド コンテキストを作成します。|

## <a name="remarks"></a>Remarks

モニカーには、ファイルへのパス名のような情報が含まれています。 モニカー オブジェクトへのポインターがあるかどうかは`IMoniker`インターフェイス、ファイルが実際に配置されている場所に関するその他の特定の情報をしなくても、特定のファイルへのアクセスを取得できます。

派生した`COleStreamFile`、`CMonikerFile`モニカーまたはモニカーに行うことができますの文字列表現を受け取り、モニカーは名前のストリームにバインドします。 読み取りし、そのストリームに書き込むことができます。 真の目的は、`CMonikerFile`簡単なアクセスを提供することです`IStream`s を付けた名前`IMoniker`s、自分でストリームにバインドする必要はありませんようにまだが`CFile`ストリームに機能します。

`CMonikerFile` ストリーム以外にバインドするのには使用できません。 使用する必要がありますストレージまたはオブジェクトにバインドする場合、`IMoniker`インターフェイスを直接します。

ストリームとモニカーの詳細については、次を参照してください[COleStreamFile](../../mfc/reference/colestreamfile-class.md)で、 *MFC リファレンス*と[IStream](/windows/desktop/api/objidl/nn-objidl-istream)と[IMoniker](/windows/desktop/api/objidl/nn-objidl-imoniker)で、。Windows SDK。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

`CMonikerFile`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

##  <a name="close"></a>  CMonikerFile::Close

デタッチ後に、ストリームを解放し、モニカーを解放する、この関数を呼び出します。

```
virtual void Close();
```

### <a name="remarks"></a>Remarks

開かれていない、または既に閉じられているストリームで呼び出すことができます。

##  <a name="cmonikerfile"></a>  CMonikerFile::CMonikerFile

`CMonikerFile` オブジェクトを構築します。

```
CMonikerFile();
```

##  <a name="createbindcontext"></a>  CMonikerFile::CreateBindContext

既定値に初期化のバインド コンテキストを作成するには、この関数を呼び出します。

```
IBindCtx* CreateBindContext(CFileException* pError);
```

### <a name="parameters"></a>パラメーター

*pError*<br/>
ファイルの例外へのポインター。 エラーが発生した場合、原因に設定されます。

### <a name="return-value"></a>戻り値

バインド コンテキストへのポインター [IBindCtx](/windows/desktop/api/objidl/nn-objidl-ibindctx)成功。 それ以外の場合に NULL の場合は、バインドします。 インスタンスが開かれた場合、`IBindHost`バインド コンテキストがから取得した、インターフェイス、 `IBindHost`。 存在する場合ありません`IBindHost`インターフェイスまたはインターフェイスは、バインド コンテキストに失敗した場合、バインド コンテキストが作成されます。 説明については、 [IBindHost](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775076\(v=vs.85\))インターフェイス、Windows SDK を参照してください。

### <a name="remarks"></a>Remarks

バインド コンテキストは、特定のモニカー バインド操作に関する情報を格納するオブジェクトです。 カスタム バインド コンテキストを提供するには、この関数をオーバーライドすることができます。

##  <a name="detach"></a>  CMonikerFile::Detach

ストリームを閉じるには、この関数を呼び出します。

```
BOOL Detach(CFileException* pError = NULL);
```

### <a name="parameters"></a>パラメーター

*pError*<br/>
ファイルの例外へのポインター。 エラーが発生した場合、原因に設定されます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

##  <a name="getmoniker"></a>  CMonikerFile::GetMoniker

現在のモニカーへのポインターを取得するには、この関数を呼び出します。

```
IMoniker* GetMoniker() const;
```

### <a name="return-value"></a>戻り値

現在のモニカー インターフェイスへのポインター ( [IMoniker](/windows/desktop/api/objidl/nn-objidl-imoniker))。

### <a name="remarks"></a>Remarks

`CMonikerFile` 、インターフェイスではありませんから返されるポインターは参照カウントをインクリメントしていません (を通じて[AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref))、モニカーがリリースされたときに、`CMonikerFile`オブジェクトを解放します。 モニカーの保持またはそれを解放する場合は、まず`AddRef`こと。

##  <a name="open"></a>  CMonikerFile::Open

ファイルまたはモニカー オブジェクトを開くには、このメンバー関数を呼び出します。

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
URL またはに開かれるファイルのファイル名。

*pError*<br/>
ファイルの例外へのポインター。 エラーが発生した場合、原因に設定されます。

*pMoniker*<br/>
モニカー インターフェイスへのポインター`IMoniker`ストリームを取得できます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

*LpszURL* Macintosh でパラメーターを使用することはできません。 のみ、 *pMoniker*のフォーム`Open`Macintosh 上で使用できます。

URL またはファイルの名前を使用することができます、 *lpszURL*パラメーター。 例:

[!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/cmonikerfile-class_1.cpp)]

\- または -

[!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/cmonikerfile-class_2.cpp)]

## <a name="see-also"></a>関連項目

[COleStreamFile クラス](../../mfc/reference/colestreamfile-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CAsyncMonikerFile クラス](../../mfc/reference/casyncmonikerfile-class.md)
