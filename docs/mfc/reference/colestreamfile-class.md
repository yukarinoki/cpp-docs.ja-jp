---
title: COleStreamFile クラス
ms.date: 11/04/2016
f1_keywords:
- COleStreamFile
- AFXOLE/COleStreamFile
- AFXOLE/COleStreamFile::COleStreamFile
- AFXOLE/COleStreamFile::Attach
- AFXOLE/COleStreamFile::CreateMemoryStream
- AFXOLE/COleStreamFile::CreateStream
- AFXOLE/COleStreamFile::Detach
- AFXOLE/COleStreamFile::GetStream
- AFXOLE/COleStreamFile::OpenStream
helpviewer_keywords:
- COleStreamFile [MFC], COleStreamFile
- COleStreamFile [MFC], Attach
- COleStreamFile [MFC], CreateMemoryStream
- COleStreamFile [MFC], CreateStream
- COleStreamFile [MFC], Detach
- COleStreamFile [MFC], GetStream
- COleStreamFile [MFC], OpenStream
ms.assetid: e4f93698-e17c-4a18-a7c0-4b4df8eb4d93
ms.openlocfilehash: 2bc943c74f456302b13db77bf28b6e4b21a5524b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62373515"
---
# <a name="colestreamfile-class"></a>COleStreamFile クラス

OLE の構造化記憶の一部として、複合ファイルのデータ ストリーム (`IStream`) を表します。

## <a name="syntax"></a>構文

```
class COleStreamFile : public CFile
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[COleStreamFile::COleStreamFile](#colestreamfile)|`COleStreamFile` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleStreamFile::Attach](#attach)|ストリームをオブジェクトに関連付けます。|
|[COleStreamFile::CreateMemoryStream](#creatememorystream)|グローバル メモリからストリームを作成し、オブジェクトに関連付けます。|
|[COleStreamFile::CreateStream](#createstream)|ストリームを作成し、オブジェクトに関連付けます。|
|[COleStreamFile::Detach](#detach)|オブジェクトからストリームの関連付けを解除します。|
|[COleStreamFile::GetStream](#getstream)|現在のストリームを返します。|
|[COleStreamFile::OpenStream](#openstream)|安全にストリームを開きオブジェクトに関連付けます。|

## <a name="remarks"></a>Remarks

`IStorage`ストリームを開くか、メモリ ストリームがない限り、作成する前にオブジェクトが存在する必要があります。

`COleStreamFile` オブジェクトの操作と同様に[CFile](../../mfc/reference/cfile-class.md)オブジェクト。

ストリームとストレージ操作の詳細については、記事を参照してください。[コンテナー。複合ファイル](../../mfc/containers-compound-files.md).

詳細については、次を参照してください。 [IStream](/windows/desktop/api/objidl/nn-objidl-istream)と[IStorage](/windows/desktop/api/objidl/nn-objidl-istorage) Windows SDK に含まれています。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`COleStreamFile`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

##  <a name="attach"></a>  COleStreamFile::Attach

指定された OLE ストリームを関連付ける、`COleStreamFile`オブジェクト。

```
void Attach(LPSTREAM lpStream);
```

### <a name="parameters"></a>パラメーター

*lpStream*<br/>
OLE ストリームを指します (`IStream`) に関連付けるオブジェクト。 Nll は指定できません。

### <a name="remarks"></a>Remarks

オブジェクトがない既にあります OLE ストリームに関連付けられています。

詳細については、次を参照してください。 [IStream](/windows/desktop/api/objidl/nn-objidl-istream) Windows SDK に含まれています。

##  <a name="colestreamfile"></a>  COleStreamFile::COleStreamFile

`COleStreamFile` オブジェクトを作成します。

```
COleStreamFile(LPSTREAM lpStream = NULL);
```

### <a name="parameters"></a>パラメーター

*lpStream*<br/>
オブジェクトに関連付けられた OLE ストリームへのポインター。

### <a name="remarks"></a>Remarks

場合*lpStream*が null の場合、OLE ストリームに関連付けられているオブジェクトは、それ以外の場合、オブジェクトは、指定された OLE ストリームに関連付けられています。

詳細については、次を参照してください。 [IStream](/windows/desktop/api/objidl/nn-objidl-istream) Windows SDK に含まれています。

##  <a name="creatememorystream"></a>  COleStreamFile::CreateMemoryStream

安全に、通常は、失敗、グローバル共有メモリ不足の新しいストリームを作成します。

```
BOOL CreateMemoryStream(CFileException* pError = NULL);
```

### <a name="parameters"></a>パラメーター

*pError*<br/>
指す、 [CFileException](../../mfc/reference/cfileexception-class.md)オブジェクトまたは作成操作の完了ステータスを示す NULL。 ストリームを作成しようとして生成される可能性のある例外を監視する場合は、このパラメーターを指定します。

### <a name="return-value"></a>戻り値

ストリームが正常に作成された場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

OLE のサブシステムによって、メモリが割り当てられます。

詳細については、次を参照してください。 [CreateStreamOnHGlobal](/windows/desktop/api/combaseapi/nf-combaseapi-createstreamonhglobal) Windows SDK に含まれています。

##  <a name="createstream"></a>  COleStreamFile::CreateStream

指定されたストレージ オブジェクトが、通常は失敗で新しいストリームを安全に作成します。

```
BOOL CreateStream(
    LPSTORAGE lpStorage,
    LPCTSTR lpszStreamName,
    DWORD nOpenFlags = modeReadWrite|shareExclusive|modeCreate,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>パラメーター

*lpStorage*<br/>
作成されるストリームを含む OLE ストレージ オブジェクトへのポインター。 Nll は指定できません。

*lpszStreamName*<br/>
作成されるストリームの名前です。 Nll は指定できません。

*nOpenFlags*<br/>
ストリームを開くときに使用するアクセス モード。 排他、読み取り/書き込み、および作成モードは既定で使用します。 使用可能なモードの完全な一覧を参照してください。[ほか](../../mfc/reference/cfile-class.md#cfile)します。

*pError*<br/>
指す、 [CFileException](../../mfc/reference/cfileexception-class.md)オブジェクトまたは NULL。 ストリームを作成しようとして生成される可能性のある例外を監視する場合は、このパラメーターを指定します。

### <a name="return-value"></a>戻り値

ストリームが正常に作成された場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

オープンに失敗した場合、ファイルの例外がスローされます、 *pError*が NULL でないです。

詳細については、次を参照してください。 [IStorage::CreateStream](/windows/desktop/api/objidl/nf-objidl-istorage-createstream) Windows SDK に含まれています。

##  <a name="detach"></a>  COleStreamFile::Detach

ストリームを閉じずに、オブジェクトからストリームの関連付けを解除します。

```
LPSTREAM Detach();
```

### <a name="return-value"></a>戻り値

ストリームへのポインター (`IStream`) が、オブジェクトに関連付けられています。

### <a name="remarks"></a>Remarks

プログラムが終了する前に、その他のなんらかの方法でストリームを閉じる必要があります。

詳細については、次を参照してください。 [IStream](/windows/desktop/api/objidl/nn-objidl-istream) Windows SDK に含まれています。

##  <a name="getstream"></a>  COleStreamFile::GetStream

この関数では、現在のストリームへのポインターを返します。

```
IStream* GetStream() const;
```

### <a name="return-value"></a>戻り値

現在のストリーム インターフェイスへのポインター ( [IStream](/windows/desktop/api/objidl/nn-objidl-istream))。

##  <a name="openstream"></a>  COleStreamFile::OpenStream

既存のストリームを開きます。

```
BOOL OpenStream(
    LPSTORAGE lpStorage,
    LPCTSTR lpszStreamName,
    DWORD nOpenFlags = modeReadWrite|shareExclusive,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>パラメーター

*lpStorage*<br/>
開かれるストリームを含む OLE ストレージ オブジェクトへのポインター。 Nll は指定できません。

*lpszStreamName*<br/>
開かれるストリームの名前です。 Nll は指定できません。

*nOpenFlags*<br/>
ストリームを開くときに使用するアクセス モード。 排他的読み取り/書き込みモードは既定で使用されます。 使用可能なモードの完全な一覧で、次を参照してください。[ほか](../../mfc/reference/cfile-class.md#cfile)します。

*pError*<br/>
指す、 [CFileException](../../mfc/reference/cfileexception-class.md)オブジェクトまたは NULL。 ストリームを開こうとしたによって生成される可能性のある例外を監視する場合は、このパラメーターを指定します。

### <a name="return-value"></a>戻り値

ストリームが正常に開かれている場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

オープンに失敗した場合、ファイルの例外がスローされます、 *pError*が NULL でないです。

詳細については、次を参照してください。 [IStorage::OpenStream](/windows/desktop/api/objidl/nf-objidl-istorage-openstream) Windows SDK に含まれています。

## <a name="see-also"></a>関連項目

[CFile クラス](../../mfc/reference/cfile-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
