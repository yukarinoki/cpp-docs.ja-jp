---
title: クラス一時ファイル
ms.date: 11/04/2016
f1_keywords:
- CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile::CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile::Close
- ATLFILE/ATL::CAtlTemporaryFile::Create
- ATLFILE/ATL::CAtlTemporaryFile::Flush
- ATLFILE/ATL::CAtlTemporaryFile::GetPosition
- ATLFILE/ATL::CAtlTemporaryFile::GetSize
- ATLFILE/ATL::CAtlTemporaryFile::HandsOff
- ATLFILE/ATL::CAtlTemporaryFile::HandsOn
- ATLFILE/ATL::CAtlTemporaryFile::LockRange
- ATLFILE/ATL::CAtlTemporaryFile::Read
- ATLFILE/ATL::CAtlTemporaryFile::Seek
- ATLFILE/ATL::CAtlTemporaryFile::SetSize
- ATLFILE/ATL::CAtlTemporaryFile::TempFileName
- ATLFILE/ATL::CAtlTemporaryFile::UnlockRange
- ATLFILE/ATL::CAtlTemporaryFile::Write
helpviewer_keywords:
- CAtlTemporaryFile class
ms.assetid: 05f0f2a5-94f6-4594-8dae-b114292ff5f9
ms.openlocfilehash: 605e4bcbe7208b18d8d1a50507e8e142a93bde5e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321306"
---
# <a name="catltemporaryfile-class"></a>クラス一時ファイル

このクラスは、一時ファイルを作成および使用するためのメソッドを提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CAtlTemporaryFile
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[一時ファイル::CAtlTemporaryファイル](#catltemporaryfile)|コンストラクターです。|
|[一時ファイル::~CAtl 一時ファイル](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[一時ファイル::閉じる](#close)|一時ファイルを閉じ、その内容を削除するか、指定したファイル名で保存します。|
|[一時ファイル::作成](#create)|一時ファイルを作成します。|
|[一時ファイル::フラッシュ](#flush)|ファイル バッファーに残っているデータを強制的に一時ファイルに書き込みます。|
|[一時ファイル::取得位置](#getposition)|現在のファイル ポインターの位置を取得します。|
|[一時ファイル::ゲットサイズ](#getsize)|一時ファイルのサイズ (バイト単位) を取得します。|
|[一時的なファイル::ハンズオフ](#handsoff)|`CAtlTemporaryFile`オブジェクトとファイルの関連付けを解除します。|
|[一時的なファイル::ハンズオン](#handson)|既存の一時ファイルを開き、ファイルの末尾にポインタを置きます。|
|[一時的なファイル::ロックレンジ](#lockrange)|他のプロセスがアクセスできないように、ファイル内の領域をロックします。|
|[一時ファイル::読み取り](#read)|ファイル ポインターで指定された位置から始まる一時ファイルからデータを読み取ります。|
|[一時ファイル::シーク](#seek)|一時ファイルのファイル ポインタを移動します。|
|[一時ファイル::セットサイズ](#setsize)|一時ファイルのサイズを設定します。|
|[一時ファイル::一時ファイル名](#tempfilename)|一時ファイルの名前を返します。|
|[一時ファイル::ロック解除範囲](#unlockrange)|一時ファイルの領域をロック解除します。|
|[一時ファイル::書き込み](#write)|ファイル ポインターで指定された位置から始まる一時ファイルにデータを書き込みます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[一時ファイル::演算子ハンドル](#operator_handle)|一時ファイルへのハンドルを返します。|

## <a name="remarks"></a>解説

`CAtlTemporaryFile`一時ファイルの作成と使用が容易になります。 ファイルには、自動的に名前が付けられ、開かれ、閉じられ、削除されます。 ファイルを閉じた後にファイルの内容が必要な場合は、指定した名前の新しいファイルに保存できます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlfile.h

## <a name="example"></a>例

[次](#catltemporaryfile)の例を参照してください。

## <a name="catltemporaryfilecatltemporaryfile"></a><a name="catltemporaryfile"></a>一時ファイル::CAtlTemporaryファイル

コンストラクターです。

```
CAtlTemporaryFile() throw();
```

### <a name="remarks"></a>解説

[ファイルは、CAtlTemporaryFile::Create](#create)への呼び出しが行われるまで、実際には開かれていない。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#73](../../atl/codesnippet/cpp/catltemporaryfile-class_1.cpp)]

## <a name="catltemporaryfilecatltemporaryfile"></a><a name="dtor"></a>一時ファイル::~CAtl 一時ファイル

デストラクターです。

```
~CAtlTemporaryFile() throw();
```

### <a name="remarks"></a>解説

デストラクタは[CAtlTemporaryFile::Close](#close)を呼び出します。

## <a name="catltemporaryfileclose"></a><a name="close"></a>一時ファイル::閉じる

一時ファイルを閉じ、その内容を削除するか、指定したファイル名で保存します。

```
HRESULT Close(LPCTSTR szNewName = NULL) throw();
```

### <a name="parameters"></a>パラメーター

*新しい名前*<br/>
一時ファイルの内容を格納する新しいファイルの名前。 この引数が NULL の場合、一時ファイルの内容は削除されます。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="example"></a>例

[次](#catltemporaryfile)の例を参照してください。

## <a name="catltemporaryfilecreate"></a><a name="create"></a>一時ファイル::作成

一時ファイルを作成します。

```
HRESULT Create(LPCTSTR pszDir = NULL, DWORD dwDesiredAccess = GENERIC_WRITE) throw();
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
一時ファイルのパス。 これが NULL の場合は、パスを割り当てる[には GetTempPath](/windows/win32/api/fileapi/nf-fileapi-gettemppathw)が呼び出されます。

*アクセスを許可*<br/>
目的のアクセス。 Windows SDK の[「ファイルの作成](/windows/win32/api/fileapi/nf-fileapi-createfilew)」の*dwDesiredAccess*を参照してください。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="example"></a>例

[次](#catltemporaryfile)の例を参照してください。

## <a name="catltemporaryfileflush"></a><a name="flush"></a>一時ファイル::フラッシュ

ファイル バッファーに残っているデータを強制的に一時ファイルに書き込みます。

```
HRESULT Flush() throw();
```

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

ファイルが閉じられていないことを除いて[、CAtlTemporaryFile::ハンズオフ](#handsoff)と同様です。

### <a name="example"></a>例

[次](#catltemporaryfile)の例を参照してください。

## <a name="catltemporaryfilegetposition"></a><a name="getposition"></a>一時ファイル::取得位置

現在のファイル ポインターの位置を取得します。

```
HRESULT GetPosition(ULONGLONG& nPos) const throw();
```

### <a name="parameters"></a>パラメーター

*Npo*<br/>
バイト単位の位置。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

ファイル ポインタの位置を変更するには[、CAtlTemporaryFile::Seek](#seek)を使用します。

## <a name="catltemporaryfilegetsize"></a><a name="getsize"></a>一時ファイル::ゲットサイズ

一時ファイルのサイズ (バイト単位) を取得します。

```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```

### <a name="parameters"></a>パラメーター

*nlen*<br/>
ファイル内のバイト数。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="catltemporaryfilehandsoff"></a><a name="handsoff"></a>一時的なファイル::ハンズオフ

`CAtlTemporaryFile`オブジェクトとファイルの関連付けを解除します。

```
HRESULT HandsOff() throw();
```

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

`HandsOff`および[CAtlTemporaryFile::HandsOn](#handson)は、オブジェクトからファイルの関連付けを解除し、必要に応じて再アタッチするために使用されます。 `HandsOff`ファイル バッファに残っているデータを強制的に一時ファイルに書き込み、ファイルを閉じます。 ファイルを完全に閉じて削除する場合、またはファイルの内容を指定した名前で閉じて保持する場合は[、CAtlTemporaryFile::Close](#close)を使用します。

## <a name="catltemporaryfilehandson"></a><a name="handson"></a>一時的なファイル::ハンズオン

既存の一時ファイルを開き、ファイルの末尾にポインタを置きます。

```
HRESULT HandsOn() throw();
```

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

[CAtlTemporaryFile::ハンズオフ](#handsoff)は`HandsOn`、オブジェクトからファイルの関連付けを解除し、必要に応じて再アタッチするために使用されます。

## <a name="catltemporaryfilelockrange"></a><a name="lockrange"></a>一時的なファイル::ロックレンジ

一時ファイル内の領域をロックして、他のプロセスがアクセスできないようにします。

```
HRESULT LockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>パラメーター

*Npo*<br/>
ロックを開始するファイル内の位置。

*nカウント*<br/>
ロックするバイト範囲の長さ。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

ファイル内のバイトをロックすると、他のプロセスがそれらのバイトにアクセスできなくなります。 ファイルの複数の領域をロックできますが、重複する領域は使用できません。 領域のロックを解除するには[、CAtlTemporaryFile::UnlockRange](#unlockrange)を使用して、バイト範囲が以前にロックされていた領域に正確に対応していることを確認します。 `LockRange`隣接する領域はマージされません。2 つのロックされた領域が隣接している場合は、それぞれ個別にロックを解除する必要があります。

## <a name="catltemporaryfileoperator-handle"></a><a name="operator_handle"></a>一時ファイル::演算子ハンドル

一時ファイルへのハンドルを返します。

```
operator HANDLE() throw();
```

## <a name="catltemporaryfileread"></a><a name="read"></a>一時ファイル::読み取り

ファイル ポインターで指定された位置から始まる一時ファイルからデータを読み取ります。

```
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();
```

### <a name="parameters"></a>パラメーター

*pBuffer*<br/>
ファイルから読み取ったデータを受け取るバッファーへのポインター。

*サイズを変更します。*<br/>
バイト単位のバッファー サイズ。

*バイト読み取り*<br/>
読み取るバイト数。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

を呼び出します[。](../../atl/reference/catlfile-class.md#read) ファイル ポインタの位置を変更するには[、CAtlTemporaryFile::Seek](#seek)を呼び出します。

### <a name="example"></a>例

[次](#catltemporaryfile)の例を参照してください。

## <a name="catltemporaryfileseek"></a><a name="seek"></a>一時ファイル::シーク

一時ファイルのファイル ポインタを移動します。

```
HRESULT Seek(LONGLONG nOffset, DWORD dwFrom = FILE_CURRENT) throw();
```

### <a name="parameters"></a>パラメーター

*オフセット*<br/>
*dwFrom*で指定された開始点からのオフセット (バイト単位)。

*dwから*<br/>
開始点 (FILE_BEGIN、FILE_CURRENT、またはFILE_END)。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

を呼び出します[。](../../atl/reference/catlfile-class.md#seek) 現在のファイル ポインタの位置を取得するには[、CAtlTemporaryFile::GetPosition](#getposition)を呼び出します。

### <a name="example"></a>例

[次](#catltemporaryfile)の例を参照してください。

## <a name="catltemporaryfilesetsize"></a><a name="setsize"></a>一時ファイル::セットサイズ

一時ファイルのサイズを設定します。

```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```

### <a name="parameters"></a>パラメーター

*nニューレン*<br/>
ファイルの新しい長さ (バイト単位)。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

を呼び出します[。](../../atl/reference/catlfile-class.md#setsize) 戻り値の場合、ファイル ポインタはファイルの末尾に置かれる。

## <a name="catltemporaryfiletempfilename"></a><a name="tempfilename"></a>一時ファイル::一時ファイル名

一時ファイルの名前を返します。

```
LPCTSTR TempFileName() throw();
```

### <a name="return-value"></a>戻り値

ファイル名を指す LPCTSTR を返します。

### <a name="remarks"></a>解説

ファイル名は、関数を[呼](/windows/win32/api/fileapi/nf-fileapi-gettempfilenamew)び出して[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)で生成されます。 ファイル拡張子は、常に一時ファイルの場合は"TFR"になります。

## <a name="catltemporaryfileunlockrange"></a><a name="unlockrange"></a>一時ファイル::ロック解除範囲

一時ファイルの領域をロック解除します。

```
HRESULT UnlockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>パラメーター

*Npo*<br/>
ファイル内でのロック解除の開始位置。

*nカウント*<br/>
ロック解除するバイト範囲の長さ。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

を呼び出します[。](../../atl/reference/catlfile-class.md#unlockrange)

## <a name="catltemporaryfilewrite"></a><a name="write"></a>一時ファイル::書き込み

ファイル ポインターで指定された位置から始まる一時ファイルにデータを書き込みます。

```
HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();
```

### <a name="parameters"></a>パラメーター

*pBuffer*<br/>
ファイルに書き込むデータを格納しているバッファー。

*サイズを変更します。*<br/>
バッファーから転送されるバイト数。

*書き込まれたバイト*<br/>
書き込まれたバイト数。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

を呼び出します[。](../../atl/reference/catlfile-class.md#write)

### <a name="example"></a>例

[次](#catltemporaryfile)の例を参照してください。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[クラス](../../atl/reference/catlfile-class.md)
