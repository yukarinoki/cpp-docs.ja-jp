---
title: クラス
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
ms.openlocfilehash: 1f53d3bd55fbff45257c06af2ab11f066d421a54
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376095"
---
# <a name="colestreamfile-class"></a>クラス

OLE の構造化記憶の一部として、複合ファイルのデータ ストリーム (`IStream`) を表します。

## <a name="syntax"></a>構文

```
class COleStreamFile : public CFile
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ファイルをストリームします。](#colestreamfile)|`COleStreamFile` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ファイルを添付します。](#attach)|ストリームをオブジェクトに関連付けます。|
|[ファイル::メモリストリームを作成します。](#creatememorystream)|グローバル メモリからストリームを作成し、オブジェクトに関連付けます。|
|[ファイルを作成します。](#createstream)|ストリームを作成し、オブジェクトに関連付けます。|
|[コレストリームファイル::Dエタッハ](#detach)|オブジェクトからストリームの関連付けを解除します。|
|[ファイルを取得します。](#getstream)|現在のストリームを返します。|
|[ファイルを開く](#openstream)|ストリームを安全に開き、オブジェクトに関連付けます。|

## <a name="remarks"></a>解説

オブジェクト`IStorage`は、ストリームを開いたり作成したりするには、そのストリームがメモリ ストリームでない限り、あらかじめ存在している必要があります。

`COleStreamFile`オブジェクトは[CFile](../../mfc/reference/cfile-class.md)オブジェクトとまったく同じように操作されます。

ストリームとストレージの操作の詳細については、「[コンテナー: 複合ファイル](../../mfc/containers-compound-files.md)」を参照してください。

詳細については、Windows SDK の[IStream](/windows/win32/api/objidl/nn-objidl-istream)と[IStorage](/windows/win32/api/objidl/nn-objidl-istorage)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`COleStreamFile`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

## <a name="colestreamfileattach"></a><a name="attach"></a>ファイルを添付します。

指定された OLE ストリームをオブジェクト`COleStreamFile`に関連付けます。

```
void Attach(LPSTREAM lpStream);
```

### <a name="parameters"></a>パラメーター

*lpStream*<br/>
オブジェクトに関連付ける`IStream`OLE ストリーム ( ) へのポイント。 Nll は指定できません。

### <a name="remarks"></a>解説

オブジェクトは、OLE ストリームに関連付けられていない必要があります。

詳細については、Windows SDK の[「IStream」](/windows/win32/api/objidl/nn-objidl-istream)を参照してください。

## <a name="colestreamfilecolestreamfile"></a><a name="colestreamfile"></a>ファイルをストリームします。

`COleStreamFile` オブジェクトを作成します。

```
COleStreamFile(LPSTREAM lpStream = NULL);
```

### <a name="parameters"></a>パラメーター

*lpStream*<br/>
オブジェクトに関連付ける OLE ストリームへのポインター。

### <a name="remarks"></a>解説

*lpStream*が NULL の場合、オブジェクトは OLE ストリームに関連付けされません。

詳細については、Windows SDK の[「IStream」](/windows/win32/api/objidl/nn-objidl-istream)を参照してください。

## <a name="colestreamfilecreatememorystream"></a><a name="creatememorystream"></a>ファイル::メモリストリームを作成します。

グローバルな共有メモリから新しいストリームを安全に作成します。

```
BOOL CreateMemoryStream(CFileException* pError = NULL);
```

### <a name="parameters"></a>パラメーター

*pError*<br/>
作成操作の完了状態を示す[CFileException](../../mfc/reference/cfileexception-class.md)オブジェクトまたは NULL を指します。 ストリームの作成を試みることによって生成される可能性のある例外をモニターする場合は、このパラメーターを指定します。

### <a name="return-value"></a>戻り値

ストリームが正常に作成された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

メモリは OLE サブシステムによって割り当てられます。

詳細については、Windows SDK[の「グローバルな作成](/windows/win32/api/combaseapi/nf-combaseapi-createstreamonhglobal)」を参照してください。

## <a name="colestreamfilecreatestream"></a><a name="createstream"></a>ファイルを作成します。

正常な予期される状態である場合、指定されたストレージ オブジェクトに新しいストリームを安全に作成します。

```
BOOL CreateStream(
    LPSTORAGE lpStorage,
    LPCTSTR lpszStreamName,
    DWORD nOpenFlags = modeReadWrite|shareExclusive|modeCreate,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>パラメーター

*lp ストレージ*<br/>
作成するストリームを含む OLE ストレージ オブジェクトへのポイント。 Nll は指定できません。

*名前を変更します。*<br/>
作成するストリームの名前。 Nll は指定できません。

*フラグを開く*<br/>
ストリームを開くときに使用するアクセス モード。 排他モード、読み取り/書き込みモード、作成モードがデフォルトで使用されます。 使用可能なモードの完全な一覧については[、「CFile::CFile」](../../mfc/reference/cfile-class.md#cfile)を参照してください。

*pError*<br/>
[オブジェクトまたは](../../mfc/reference/cfileexception-class.md)NULL を指します。 ストリームの作成を試みることによって生成される可能性のある例外をモニターする場合は、このパラメーターを指定します。

### <a name="return-value"></a>戻り値

ストリームが正常に作成された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

開けに失敗し *、pError*が NULL でない場合、ファイル例外がスローされます。

詳細については、Windows SDK[の「IStorage::CreateStream」](/windows/win32/api/objidl/nf-objidl-istorage-createstream)を参照してください。

## <a name="colestreamfiledetach"></a><a name="detach"></a>コレストリームファイル::Dエタッハ

ストリームを閉じずに、オブジェクトからストリームの関連付けを解除します。

```
LPSTREAM Detach();
```

### <a name="return-value"></a>戻り値

オブジェクトに関連付けられたストリーム`IStream`( ) へのポインター。

### <a name="remarks"></a>解説

プログラムが終了する前に、ストリームを他の方法で閉じる必要があります。

詳細については、Windows SDK の[「IStream」](/windows/win32/api/objidl/nn-objidl-istream)を参照してください。

## <a name="colestreamfilegetstream"></a><a name="getstream"></a>ファイルを取得します。

現在のストリームへのポインターを返します。

```
IStream* GetStream() const;
```

### <a name="return-value"></a>戻り値

現在のストリーム インターフェイス ( [IStream](/windows/win32/api/objidl/nn-objidl-istream)) へのポインター。

## <a name="colestreamfileopenstream"></a><a name="openstream"></a>ファイルを開く

既存のストリームを開きます。

```
BOOL OpenStream(
    LPSTORAGE lpStorage,
    LPCTSTR lpszStreamName,
    DWORD nOpenFlags = modeReadWrite|shareExclusive,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>パラメーター

*lp ストレージ*<br/>
開くストリームを含む OLE ストレージ オブジェクトへのポイント。 Nll は指定できません。

*名前を変更します。*<br/>
開くストリームの名前。 Nll は指定できません。

*フラグを開く*<br/>
ストリームを開くときに使用するアクセス モード。 排他モードと読み取り/書き込みモードは、既定で使用されます。 使用可能なモードの完全な一覧については[、「CFile::CFile」](../../mfc/reference/cfile-class.md#cfile)を参照してください。

*pError*<br/>
[オブジェクトまたは](../../mfc/reference/cfileexception-class.md)NULL を指します。 ストリームを開こうとして生成される例外をモニターする場合は、このパラメーターを指定します。

### <a name="return-value"></a>戻り値

ストリームが正常に開かれた場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

開けに失敗し *、pError*が NULL でない場合、ファイル例外がスローされます。

詳細については、Windows SDK[の「IStorage::OpenStream」](/windows/win32/api/objidl/nf-objidl-istorage-openstream)を参照してください。

## <a name="see-also"></a>関連項目

[CFile クラス](../../mfc/reference/cfile-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
