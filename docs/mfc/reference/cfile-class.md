---
title: CFile クラス
ms.date: 06/12/2018
f1_keywords:
- CFile
- AFX/CFile
- AFX/CFile::CFile
- AFX/CFile::Abort
- AFX/CFile::Close
- AFX/CFile::Duplicate
- AFX/CFile::Flush
- AFX/CFile::GetFileName
- AFX/CFile::GetFilePath
- AFX/CFile::GetFileTitle
- AFX/CFile::GetLength
- AFX/CFile::GetPosition
- AFX/CFile::GetStatus
- AFX/CFile::LockRange
- AFX/CFile::Open
- AFX/CFile::Read
- AFX/CFile::Remove
- AFX/CFile::Rename
- AFX/CFile::Seek
- AFX/CFile::SeekToBegin
- AFX/CFile::SeekToEnd
- AFX/CFile::SetFilePath
- AFX/CFile::SetLength
- AFX/CFile::SetStatus
- AFX/CFile::UnlockRange
- AFX/CFile::Write
- AFX/CFile::hFileNull
- AFX/CFile::m_hFile
- AFX/CFile::m_pTM
helpviewer_keywords:
- CFile [MFC], CFile
- CFile [MFC], Abort
- CFile [MFC], Close
- CFile [MFC], Duplicate
- CFile [MFC], Flush
- CFile [MFC], GetFileName
- CFile [MFC], GetFilePath
- CFile [MFC], GetFileTitle
- CFile [MFC], GetLength
- CFile [MFC], GetPosition
- CFile [MFC], GetStatus
- CFile [MFC], LockRange
- CFile [MFC], Open
- CFile [MFC], Read
- CFile [MFC], Remove
- CFile [MFC], Rename
- CFile [MFC], Seek
- CFile [MFC], SeekToBegin
- CFile [MFC], SeekToEnd
- CFile [MFC], SetFilePath
- CFile [MFC], SetLength
- CFile [MFC], SetStatus
- CFile [MFC], UnlockRange
- CFile [MFC], Write
- CFile [MFC], hFileNull
- CFile [MFC], m_hFile
- CFile [MFC], m_pTM
ms.assetid: b2eb5757-d499-4e67-b044-dd7d1abaa0f8
ms.openlocfilehash: 4ba37d481db73fb0556659ede267b3474c3f32f5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373916"
---
# <a name="cfile-class"></a>CFile クラス

ファイルに関する MFC の基底クラスです。

## <a name="syntax"></a>構文

```
class CFile : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ファイル::Cファイル](#cfile)|パスまたはファイル`CFile`ハンドルからオブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cファイル::中止](#abort)|警告とエラーをすべて無視してファイルを閉じます。|
|[ファイル::閉じる](#close)|ファイルを閉じてオブジェクトを削除します。|
|[ファイル::D](#duplicate)|このファイルに基づいて、重複するオブジェクトを作成します。|
|[ファイル::フラッシュ](#flush)|書き込みがまだ行われていないデータをフラッシュします。|
|[ファイル名::ファイル名を取得します。](#getfilename)|選択したファイルのファイル名を取得します。|
|[ファイル::ファイルパスを取得します。](#getfilepath)|選択したファイルの完全なファイル パスを取得します。|
|[ファイル::ファイルタイトルを取得します。](#getfiletitle)|選択したファイルのタイトルを取得します。|
|[ファイル::ゲットレングス](#getlength)|ファイルの長さを取得します。|
|[ファイル::取得位置](#getposition)|現在のファイル ポインターを取得します。|
|[ファイル::ステータスを取得します。](#getstatus)|開いているファイルの状態を取得するか、静的バージョンで、指定したファイル (静的、仮想関数) の状態を取得します。|
|[ファイル::ロックレンジ](#lockrange)|ファイル内のバイトの範囲をロックします。|
|[ファイル::開く](#open)|エラー テスト オプションを使用してファイルを安全に開きます。|
|[ファイル::読み取り](#read)|現在のファイル位置にあるファイルからデータを読み取ります (バッファされていない)。|
|[ファイル::削除](#remove)|指定したファイルを削除します (静的関数)。|
|[Cファイル::名前の変更](#rename)|指定したファイルの名前を変更します (静的関数)。|
|[ファイル::シーク](#seek)|現在のファイル ポインタを配置します。|
|[ファイル::シークトビギン](#seektobegin)|現在のファイル ポインタをファイルの先頭に配置します。|
|[ファイル::シークトーエンド](#seektoend)|現在のファイル ポインタをファイルの末尾に配置します。|
|[ファイル::セットファイルパス](#setfilepath)|選択したファイルの完全なファイル パスを設定します。|
|[ファイル::セットレングス](#setlength)|ファイルの長さを変更します。|
|[ファイル::セットステータス](#setstatus)|指定したファイルのステータスを設定します (静的関数、仮想関数)。|
|[ファイル::ロック解除範囲](#unlockrange)|ファイル内のバイト範囲のロックを解除します。|
|[ファイル::書き込み](#write)|ファイル内のデータを現在のファイル位置に書き込みます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[Cファイル::演算子ハンドル](#operator_handle)|`CFile`オブジェクトへのハンドル。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ファイル::hファイルNull](#hfilenull)|オブジェクトが`CFile`有効なハンドルを持つかどうかを判断します。|
|[ファイル::m_hFile](#m_hfile)|通常は、オペレーティング システムのファイル ハンドルが含まれています。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[ファイル::m_pTM](#m_ptm)|オブジェクトへの`CAtlTransactionManager`ポインター。|

## <a name="remarks"></a>解説

バッファされていないバイナリ ディスク入出力サービスを直接提供し、間接的に派生クラスを通じてテキスト ファイルとメモリ ファイルをサポートします。 `CFile`この`CArchive`クラスと連携して、Microsoft Foundation クラス オブジェクトのシリアル化をサポートします。

このクラスとその派生クラスの間の階層的な関係により、プログラムはポリモーフィック`CFile`インターフェイスを通じてすべてのファイル オブジェクトを操作できます。 たとえば、メモリ ファイルはディスク ファイルのように動作します。

汎用`CFile`ディスク I/O に使用し、その派生クラスを使用します。 ディスク`ofstream`ファイルに`iostream`送信される書式付きテキストに使用するクラスまたはその他の Microsoft クラス。

通常、ディスクファイルは構築時に自動的に`CFile`開かれ、破壊時に閉じられます。 静的メンバー関数を使用すると、ファイルを開かずにファイルの状態を調べられます。

`CFile`の使用方法の詳細については、『 ランタイム ライブラリ リファレンス 』[の「MFC のファイル](../../mfc/files-in-mfc.md)」および[「ファイル処理](../../c-runtime-library/file-handling.md)」を*参照してください*。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CFile`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="cfileabort"></a><a name="abort"></a>Cファイル::中止

このオブジェクトに関連付けられたファイルを閉じ、ファイルを読み取りまたは書き込みできないようにします。

```
virtual void Abort();
```

### <a name="remarks"></a>解説

オブジェクトを破棄する前にファイルを閉じなければ、デストラクタはファイルを閉じます。

例外を処理する場合、2`CFile::Abort`つの`CFile::Close`重要な点で異なります。 まず、失敗`Abort`は`Abort`無視されるため、関数はエラー時に例外をスローしません。 次に`Abort`、ファイルが開かれていない場合、または以前に閉じられた場合は **、ASSERT**しません。

**new**を使用してヒープに`CFile`オブジェクトを割り当てた場合は、ファイルを閉じた後で削除する必要があります。 `Abort`に`m_hFile`設定`CFile::hFileNull`されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#5](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_1.cpp)]

## <a name="cfilecfile"></a><a name="cfile"></a>ファイル::Cファイル

`CFile` オブジェクトを構築して初期化します。

```
CFile();
CFile(CAtlTransactionManager* pTM);
CFile(HANDLE hFile);

CFile(
LPCTSTR lpszFileName,
UINT nOpenFlags);

CFile(
LPCTSTR lpszFileName,
UINT nOpenFlags,
CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>パラメーター

*hファイル*<br/>
`CFile` オブジェクトにアタッチするためのファイル ハンドル。

*ファイル名*<br/>
`CFile` オブジェクトにアタッチするための相対パスまたは完全パス。

*フラグを開く*<br/>
指定されたファイルのファイル アクセス オプションのビットごとの組み合わせ (OR)。 使用できるオプションについては、「解説」を参照してください。

*Ptm*<br/>
CAtlTransactionManager オブジェクトへのポインター。

### <a name="remarks"></a>解説

次の 5 つの表は *、nOpenFlags*パラメーターに使用できるオプションを示しています。

次のファイル アクセス モード オプションから 1 つのみ選択します。 既定のファイル アクセス モードは `CFile::modeRead` であり、これは読み取り専用です。

|[値]|説明|
|-----------|-----------------|
|`CFile::modeRead`|読み取りアクセスのみを要求します。|
|`CFile::modeWrite`|書き込みアクセスのみを要求します。|
|`CFile::modeReadWrite`|読み取りおよび書き込みアクセスを要求します。|

次の文字モード オプションのいずれかを選択します。

|[値]|説明|
|-----------|-----------------|
|`CFile::typeBinary`|バイナリ モードを設定します (派生クラスのみで使用されます)。|
|`CFile::typeText`|キャリッジ リターンとライン フィードのペア (派生クラスでのみ使用) の特別な処理を使用して、テキスト モードを設定します。|
|`CFile::typeUnicode`|Unicode モードを設定します (派生クラスのみで使用されます)。 アプリケーションが Unicode 構成でビルドされた場合、テキストは Unicode 形式でファイルに書き込まれます。 BOM はファイルに書き込まれません。|

次のファイル共有モード オプションから 1 つのみ選択します。 既定のファイル共有モードは `CFile::shareExclusive` であり、これは排他的です。

|[値]|説明|
|-----------|-----------------|
|`CFile::shareDenyNone`|共有の制限はありません。|
|`CFile::shareDenyRead`|他のすべての読み取りアクセスを拒否します。|
|`CFile::shareDenyWrite`|他のすべての書き込みアクセスを拒否します。|
|`CFile::shareExclusive`|他のすべての読み取りおよび書き込みアクセスを拒否します。|

次のファイル作成モード オプションから最初のオプションまたは両方を選択します。 既定の作成モードは `CFile::modeNoTruncate` であり、これは既存を開くです。

|[値]|説明|
|-----------|-----------------|
|`CFile::modeCreate`|ファイルが存在しない場合は、新しいファイルを作成します。 ファイルが既に存在する場合は、上書きされ、最初は長さ 0 に設定されます。|
|`CFile::modeNoTruncate`|ファイルが存在しない場合は、新しいファイルを作成します。それ以外の場合は、ファイルが既に存在する場合は`CFile`、オブジェクトにアタッチされます。|

説明に従って次のファイル キャッシュ オプションを選択します。 デフォルトでは、オプションとして使用できない汎用キャッシュ方式が使用されます。

|[値]|説明|
|-----------|-----------------|
|`CFile::osNoBuffer`|システムはファイルの中間キャッシュを使用しません。 このオプションを選択すると、次の 2 つのオプションは取り消されます。|
|`CFile::osRandomAccess`|ファイル キャッシュはランダム アクセスに対して最適化されます。 このオプションとシーケンシャルスキャンオプションの両方を使用しないでください。|
|`CFile::osSequentialScan`|ファイル キャッシュは順次アクセスに対して最適化されます。 このオプションとランダム アクセス オプションの両方を使用しないでください。|
|`CFile::osWriteThrough`|書き込み操作は、遅延なく行われます。|

ファイル ハンドルが継承されないようにするために、次のセキュリティ オプションを選択します。 既定では、新しい子プロセスはファイル ハンドルを使用できます。

|[値]|説明|
|-----------|-----------------|
|`CFile::modeNoInherit`|子プロセスがファイル ハンドルを使用できないようにします。|

既定のコンストラクターはメンバーを初期化しますが、`CFile`オブジェクトにファイルをアタッチしません。 このコンストラクターを使用した後[、CFile::Open](#open)メソッドを使用してファイルを開き、`CFile`オブジェクトにアタッチします。

1 つのパラメーターを持つコンストラクターでは、メンバーは初期化され、既存のファイルが `CFile` オブジェクトにアタッチされます。

2 つのパラメーターを持つコンストラクターでは、メンバーは初期化され、指定されたファイルを開くことが試行されます。 このコンストラクターによって、指定されたファイルが正常に開かれると、ファイルは `CFile` オブジェクトにアタッチされます。それ以外の場合は、このコンストラクターによって `CInvalidArgException` オブジェクトへのポインターがスローされます。 例外の処理方法の詳細については、「[例外](../../mfc/exception-handling-in-mfc.md)」を参照してください。

指定した`CFile`ファイルが正常に開かれた場合、オブジェクトが破棄されると、このファイルは`CFile`自動的に閉じられます。それ以外の場合は、オブジェクトにアタッチされなくなった後に、ファイルを明示的に`CFile`閉じる必要があります。

### <a name="example"></a>例

`CFile` の使用例を次のコードに示します。

[!code-cpp[NVC_MFCFiles#4](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_2.cpp)]

## <a name="cfileclose"></a><a name="close"></a>ファイル::閉じる

このオブジェクトに関連付けられたファイルを閉じ、ファイルを読み取りまたは書き込みできないようにします。

```
virtual void Close();
```

### <a name="remarks"></a>解説

オブジェクトを破棄する前にファイルを閉じなければ、デストラクタはファイルを閉じます。

**new**を使用してヒープに`CFile`オブジェクトを割り当てた場合は、ファイルを閉じた後で削除する必要があります。 `Close`に`m_hFile`設定`CFile::hFileNull`されます。

### <a name="example"></a>例

[CFile::CFile](#cfile)の例を参照してください。

## <a name="cfileduplicate"></a><a name="duplicate"></a>ファイル::D

指定したファイルの`CFile`複製オブジェクトを作成します。

```
virtual CFile* Duplicate() const;
```

### <a name="return-value"></a>戻り値

重複オブジェクト`CFile`へのポインター。

### <a name="remarks"></a>解説

この関数は、C ランタイム関数`_dup`と同等です。

## <a name="cfileflush"></a><a name="flush"></a>ファイル::フラッシュ

ファイル バッファに残っているデータを強制的にファイルに書き込みます。

```
virtual void Flush();
```

### <a name="remarks"></a>解説

の`Flush`使用は、バッファの`CArchive`フラッシュを保証するものではありません。 アーカイブを使用している場合は、最初に[CArchive::フラッシュを](../../mfc/reference/carchive-class.md#flush)呼び出します。

### <a name="example"></a>例

[CFile::セットファイルパス](#setfilepath)の例を参照してください。

## <a name="cfilegetfilename"></a><a name="getfilename"></a>ファイル名::ファイル名を取得します。

指定したファイルの名前を取得します。

```
virtual CString GetFileName() const;
```

### <a name="return-value"></a>戻り値

ファイルの名前です。

### <a name="remarks"></a>解説

たとえば、ファイル`GetFileName``c:\windows\write\myfile.wri`に関するメッセージをユーザーに生成するために呼び出すと、ファイル名`myfile.wri`、 が返されます。

ファイルのパス全体を取得するには、名前を含めて[GetFilePath](#getfilepath)を呼び出します。 ファイルのタイトルを返す場合`myfile`( )[を呼び](#getfiletitle)出します。

### <a name="example"></a>例

このコードフラグメントは、システムを開きます。INI ファイルを WINDOWS ディレクトリに保存します。 見つかった場合、この例は「出力」に示すように、名前とパスとタイトルを出力します。

[!code-cpp[NVC_MFCFiles#6](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_3.cpp)]

## <a name="cfilegetfilepath"></a><a name="getfilepath"></a>ファイル::ファイルパスを取得します。

指定したファイルの完全パスを取得します。

```
virtual CString GetFilePath() const;
```

### <a name="return-value"></a>戻り値

指定したファイルの完全パス。

### <a name="remarks"></a>解説

たとえば、ファイルに関する`GetFilePath`メッセージをユーザーに生成するために呼び出すと`c:\windows\write\myfile.wri`、ファイル パス`c:\windows\write\myfile.wri`、 が返されます。

ファイルの名前だけを返す場合は、`myfile.wri` [GetFileName](#getfilename)を呼び出します。 ファイルのタイトルを返す場合`myfile`( )[を呼び](#getfiletitle)出します。

### <a name="example"></a>例

[「ファイル名の取得](#getfilename)」の例を参照してください。

## <a name="cfilegetfiletitle"></a><a name="getfiletitle"></a>ファイル::ファイルタイトルを取得します。

ファイルのファイル タイトル (表示名) を取得します。

```
virtual CString GetFileTitle() const;
```

### <a name="return-value"></a>戻り値

基になるファイルのタイトル。

### <a name="remarks"></a>解説

このメソッドは、ファイルのタイトルを取得するために[GetFileTitle](/windows/win32/api/commdlg/nf-commdlg-getfiletitlew)を呼び出します。 成功した場合、このメソッドは、システムがファイル名をユーザーに表示するために使用する文字列を返します。 それ以外の場合、メソッドは[PathFindFileName](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew)を呼び出して、基になるファイルのファイル名 (ファイル拡張子を含む) を取得します。 つまり、ファイル拡張子が返されるファイル タイトル文字列に必ずしも含まれているとは限りません。 詳細については、Windows SDK[の「ファイル タイトル](/windows/win32/api/commdlg/nf-commdlg-getfiletitlew)と[パス検索ファイル名](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew)」を参照してください。

ファイルのパス全体を取得するには、名前を含めて[GetFilePath](#getfilepath)を呼び出します。 ファイルの名前だけを返す場合は[、GetFileName](#getfilename)を呼び出します。

### <a name="example"></a>例

[「ファイル名の取得](#getfilename)」の例を参照してください。

## <a name="cfilegetlength"></a><a name="getlength"></a>ファイル::ゲットレングス

ファイルの現在の論理長をバイト単位で取得します。

```
virtual ULONGLONG GetLength() const;
```

### <a name="return-value"></a>戻り値

ファイルの長さ。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#7](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_4.cpp)]

## <a name="cfilegetposition"></a><a name="getposition"></a>ファイル::取得位置

ファイル ポインタの現在の値を`Seek`取得します。

```
virtual ULONGLONG GetPosition() const;
```

### <a name="return-value"></a>戻り値

ファイル ポインター。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#8](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_5.cpp)]

## <a name="cfilegetstatus"></a><a name="getstatus"></a>ファイル::ステータスを取得します。

このメソッドは、指定したオブジェクト インスタンスまたは`CFile`指定したファイル パスに関連するステータス情報を取得します。

```
BOOL GetStatus(CFileStatus& rStatus) const;

static BOOL PASCAL GetStatus(
    LPCTSTR lpszFileName,
    CFileStatus& rStatus,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>パラメーター

*rステータス*<br/>
状態情報を受け取る`CFileStatus`ユーザー提供の構造体への参照。 構造`CFileStatus`には、次のフィールドがあります。

- `CTime m_ctime`ファイルが作成された日時。

- `CTime m_mtime`ファイルが最後に変更された日時。

- `CTime m_atime`ファイルが読み取りのために最後にアクセスされた日時。

- `ULONGLONG m_size`DIR コマンドによって報告されるファイルの論理サイズ (バイト単位)。

- `BYTE m_attribute`ファイルの属性バイト。

- `char m_szFullName[_MAX_PATH]`Windows 文字セットの絶対ファイル名。

*ファイル名*<br/>
目的のファイルへのパスを示す Windows 文字セット内の文字列。 パスは、相対パスまたは絶対パス、またはネットワーク パス名を含めることができます。

*Ptm*<br/>
CAtlTransactionManager オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

指定したファイルの状態情報が正常に取得された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

非静的バージョンのオブジェクト`GetStatus`に関連付けられたオープン・ファイルの状況情報を取得`CFile`します。  静的バージョンのの`GetStatus`場合、ファイルを実際に開かずに指定のファイル パスからファイルのステータスを取得します。 このバージョンは、ファイルの存在権とアクセス権をテストする場合に便利です。

構造体`m_attribute`のメンバーは`CFileStatus`、ファイル属性セットを参照します。 この`CFile`クラスは **、ファイル属性**をシンボル的に指定できるように、属性列挙型を提供します。

```
enum Attribute {
    normal =    0x00,
    readOnly =  0x01,
    hidden =    0x02,
    system =    0x04,
    volume =    0x08,
    directory = 0x10,
    archive =   0x20
    };
```

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#10](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_6.cpp)]

## <a name="cfilehfilenull"></a><a name="hfilenull"></a>ファイル::hファイルNull

オブジェクトに対して有効なファイル ハンドルが`CFile`存在するかどうかを判断します。

```
static AFX_DATA const HANDLE hFileNull;
```

### <a name="remarks"></a>解説

この定数は、オブジェクトに`CFile`有効なファイル ハンドルがあるかどうかを判断するために使用されます。

次の例は、この操作を示しています。

[!code-cpp[NVC_MFCFiles#22](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_7.cpp)]

## <a name="cfilelockrange"></a><a name="lockrange"></a>ファイル::ロックレンジ

オープン・ファイル内のバイト範囲をロックし、ファイルがすでにロックされている場合は例外をスローします。

```
virtual void LockRange(
    ULONGLONG dwPos,
    ULONGLONG dwCount);
```

### <a name="parameters"></a>パラメーター

*ドウォポス*<br/>
ロックするバイト範囲の開始位置のバイト オフセット。

*カウントカウント*<br/>
ロックする範囲内のバイト数。

### <a name="remarks"></a>解説

ファイル内のバイトをロックすると、他のプロセスがそれらのバイトにアクセスできなくなります。 ファイルの複数の領域をロックできますが、重複する領域は使用できません。

メンバー関数を使用して領域の`UnlockRange`ロックを解除する場合、バイト範囲は、以前にロックされていた領域に正確に対応している必要があります。 この`LockRange`関数は隣接する領域をマージしません。 2 つのロックされた領域が隣接している場合は、各リージョンのロックを個別に解除する必要があります。

> [!NOTE]
> この関数は、-derived クラス`CMemFile`では使用できません。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]

## <a name="cfilem_hfile"></a><a name="m_hfile"></a>ファイル::m_hFile

開いているファイルのオペレーティング システム ファイル ハンドルが含まれています。

```
HANDLE m_hFile;
```

### <a name="remarks"></a>解説

`m_hFile`は、UINT 型のパブリック変数です。 ハンドルが`CFile::hFileNull`割り当てられていない場合は、オペレーティング システムに依存しない空のファイル インジケーターが含まれます。

メンバーの`m_hFile`意味は派生クラスに依存するため、の使用はお勧めしません。 `m_hFile`クラスの非ポリモーフィックな使用をサポートする便宜上パブリック メンバーにします。

## <a name="cfilem_ptm"></a><a name="m_ptm"></a>ファイル::m_pTM

`CAtlTransactionManager`オブジェクトへのポインター。

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>解説

## <a name="cfileopen"></a><a name="open"></a>ファイル::開く

オーバーロードされます。 `Open`は、既定`CFile`のコンストラクターで使用するように設計されています。

```
virtual BOOL Open(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CAtlTransactionManager* pTM,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
目的のファイルへのパスを含む文字列。 パスは、相対パス、絶対パス、またはネットワーク名 (UNC) です。

*フラグを開く*<br/>
ファイルの共有モードとアクセス モードを定義する UINT。 ファイルを開くときに実行するアクションを指定します。 オプションは、ビットごとの OR ( **&#124;** ) 演算子を使用して組み合わせることができます。 アクセス権と共有オプションが 1 つ必要です。と`modeCreate``modeNoInherit`モードはオプションです。 モード オプションの一覧については[、CFile](#cfile)コンストラクターを参照してください。

*pError*<br/>
失敗した操作の状態を受け取る既存のファイル例外オブジェクトへのポインター。

*Ptm*<br/>
CAtlTransactionManager オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

オープンが成功した場合は 0 以外。それ以外の場合は 0。 *pError*パラメーターは、0 が返された場合にのみ意味があります。

### <a name="remarks"></a>解説

2`Open`つの関数は、ファイルを開くための "安全な" メソッドであり、障害は通常の予期される状態です。

コンストラクターが`CFile`エラー条件で例外をスローしている間に、`Open`エラー条件の場合は FALSE を返します。 `Open`ただし[、CFileException](../../mfc/reference/cfileexception-class.md)オブジェクトを初期化してエラーを記述することはできます。 *pError*パラメーターを指定しない場合、または*pError*に NULL を渡`Open`した場合は、FALSE を返`CFileException`し、. 既存`CFileException`の にポインターを渡して`Open`エラーが発生すると、関数はそのエラーを説明する情報を入力します。 `Open`どちらの場合も例外はスローされません。

次の表に、`Open`の結果の可能性を示します。

|`pError`|エラーが発生しました|戻り値|コンテンツ|
|--------------|------------------------|------------------|----------------------------|
|NULL|いいえ|TRUE|該当なし|
|ptr から`CFileException`|いいえ|TRUE|変更なし|
|NULL|はい|FALSE|該当なし|
|ptr から`CFileException`|はい|FALSE|エラーを記述するために初期化|

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#13](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_9.cpp)]

[!code-cpp[NVC_MFCFiles#14](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_10.cpp)]

## <a name="cfileoperator-handle"></a><a name="operator_handle"></a>Cファイル::演算子ハンドル

この演算子を使用して、オブジェクトへのハンドル`CFile`を、を想定する[ReadFileEx](/windows/win32/api/fileapi/nf-fileapi-readfileex)や[GetFileTime](/windows/win32/api/fileapi/nf-fileapi-getfiletime)などの関数に渡`HANDLE`します。

```
operator HANDLE() const;
```

## <a name="cfileread"></a><a name="read"></a>ファイル::読み取り

オブジェクトに関連付けられたファイルからデータをバッファーに`CFile`読み込みます。

```
virtual UINT Read(
    void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>パラメーター

*lpBuf*<br/>
ファイルから読み取られたデータを受け取るユーザー指定のバッファーへのポインター。

*nカウント*<br/>
ファイルから読み取る最大バイト数。 テキスト モード ファイルの場合、復帰線フィードのペアは 1 文字としてカウントされます。

### <a name="return-value"></a>戻り値

バッファーに転送するバイト数。 すべての`CFile`クラスについて、ファイルの末尾に達した場合、戻り値は*nCount*より小さくなる可能性があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#15](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_11.cpp)]

別の例については[、「CFile::Open」を参照](#open)してください。

## <a name="cfileremove"></a><a name="remove"></a>ファイル::削除

この静的関数は、パスで指定されたファイルを削除します。

```
static void PASCAL Remove(
    LPCTSTR lpszFileName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
目的のファイルへのパスを表す文字列。 パスは、相対パスまたは絶対パスとすることができ、ネットワーク名を含むことができます。

*Ptm*<br/>
CAtlTransactionManager オブジェクトへのポインター。

### <a name="remarks"></a>解説

`Remove`ディレクトリを削除しません。

`Remove`接続されているファイルが開いている場合、またはファイルを削除できない場合、メンバー関数は例外をスローします。 この関数は DEL コマンドと同じです。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#17](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_12.cpp)]

## <a name="cfilerename"></a><a name="rename"></a>Cファイル::名前の変更

この静的関数は、指定されたファイルの名前を変更します。

```
static void PASCAL Rename(
    LPCTSTR lpszOldName,
    LPCTSTR lpszNewName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>パラメーター

*名前*<br/>
古いパス。

*新しい名前を指定します。*<br/>
新しいパス。

*Ptm*<br/>
CAtlTransactionManager オブジェクトへのポインター。

### <a name="remarks"></a>解説

ディレクトリ名を変更できません。 この関数は REN コマンドと同等です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#18](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_13.cpp)]

## <a name="cfileseek"></a><a name="seek"></a>ファイル::シーク

開いているファイル内のファイル ポインタを再配置します。

```
virtual ULONGLONG Seek(
LONGLONG lOff,
UINT nFrom);
```

### <a name="parameters"></a>パラメーター

*lオフ*<br/>
ファイル ポインタを移動するバイト数。 正の値を指定すると、ファイル ポインタはファイルの末尾に向かって移動します。負の値を指定すると、ファイル ポインタがファイルの先頭に移動します。

*nから*<br/>
求める位置。 可能な値については、「解説」を参照してください。

### <a name="return-value"></a>戻り値

メソッドが成功した場合はファイル ポインタの位置。それ以外の場合、戻り値は未定義になり、`CFileException`例外へのポインターがスローされます。

### <a name="remarks"></a>解説

次の表は *、nFrom*パラメーターの値を示しています。

|[値]|説明|
|-----------|-----------------|
|`CFile::begin`|ファイルの先頭からシークします。|
|`CFile::current`|ファイル ポインタの現在の場所からシークします。|
|`CFile::end`|ファイルの末尾からシークします。|

ファイルを開くと、ファイルポインタはファイルの先頭である0に置かれます。

ファイル ポインタは、ファイルの末尾を越えた位置に設定できます。 この場合、ファイルに書き込むまでファイルのサイズは大きくなりません。

このメソッドの例外ハンドラーは、例外が処理された後に例外オブジェクトを削除する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#9](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_14.cpp)]

## <a name="cfileseektobegin"></a><a name="seektobegin"></a>ファイル::シークトビギン

ファイル ポインタの値をファイルの先頭に設定します。

```
void SeekToBegin();
```

### <a name="remarks"></a>解説

`SeekToBegin()` は `Seek( 0L, CFile::begin )` に相当します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]

## <a name="cfileseektoend"></a><a name="seektoend"></a>ファイル::シークトーエンド

ファイル ポインタの値をファイルの論理終端に設定します。

```
ULONGLONG SeekToEnd();
```

### <a name="return-value"></a>戻り値

ファイルの長さをバイト単位で返します。

### <a name="remarks"></a>解説

`SeekToEnd()` は `CFile::Seek( 0L, CFile::end )` に相当します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]

## <a name="cfilesetfilepath"></a><a name="setfilepath"></a>ファイル::セットファイルパス

ファイルのパスを指定します。 たとえば[、CFile](../../mfc/reference/cfile-class.md)オブジェクトが構築されたときにファイルのパスが使用できない場合は、そのパスを呼`SetFilePath`び出して指定します。

```
virtual void SetFilePath(LPCTSTR lpszNewName);
```

### <a name="parameters"></a>パラメーター

*新しい名前を指定します。*<br/>
新しいパスを指定する文字列へのポインター。

### <a name="remarks"></a>解説

> [!NOTE]
> `SetFilePath`ファイルを開いたり、ファイルを作成したりすることはありません。オブジェクトを`CFile`パス名に関連付けるだけで、使用できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#20](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_16.cpp)]

## <a name="cfilesetlength"></a><a name="setlength"></a>ファイル::セットレングス

ファイルの長さを変更します。

```
virtual void SetLength(ULONGLONG dwNewLen);
```

### <a name="parameters"></a>パラメーター

*ドニューレン*<br/>
ファイルの必要な長さ (バイト単位)。 この値は、ファイルの現在の長さより大きい場合も小さくすることもできます。 ファイルは、必要に応じて拡張または切り捨てられます。

### <a name="remarks"></a>解説

> [!NOTE]
> では`CMemFile`、この関数はオブジェクトを`CMemoryException`スローする可能性があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#11](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_17.cpp)]

## <a name="cfilesetstatus"></a><a name="setstatus"></a>ファイル::セットステータス

このファイルの場所に関連付けられているファイルのステータスを設定します。

```
static void PASCAL SetStatus(
    LPCTSTR lpszFileName,
    const CFileStatus& status,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
目的のファイルへのパスを表す文字列。 パスは、相対パスまたは絶対パスとすることができ、ネットワーク名を含むことができます。

*status*<br/>
新しいステータス情報を格納するバッファ。 メンバー関数`GetStatus`を呼び出して、`CFileStatus`構造体に現在の値を事前入力し、必要に応じて変更を加えます。 値が 0 の場合、対応するステータスアイテムは更新されません。 構造体の説明については[、GetStatus](#getstatus)メンバー関数を`CFileStatus`参照してください。

*Ptm*<br/>
CAtlTransactionManager オブジェクトへのポインター。

### <a name="remarks"></a>解説

時刻を設定するには、 `m_mtime` *status*のフィールドを変更します。

ファイルの属性のみを変更しようとして`SetStatus`呼び出しを行い、ファイルステータス構造体の`m_mtime`メンバーが 0 以外の場合、属性も影響を受ける可能性があります (タイムスタンプの変更は属性に影響を与える可能性があります)。 ファイルの属性のみを変更する場合は、まずファイルステータス構造体の`m_mtime`メンバーを 0 に設定してから、 を呼び出します`SetStatus`。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#21](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_18.cpp)]

## <a name="cfileunlockrange"></a><a name="unlockrange"></a>ファイル::ロック解除範囲

開いているファイル内のバイト範囲のロックを解除します。

```
virtual void UnlockRange(
    ULONGLONG dwPos,
    ULONGLONG dwCount);
```

### <a name="parameters"></a>パラメーター

*ドウォポス*<br/>
ロック解除するバイト範囲の開始位置のバイト オフセット。

*カウントカウント*<br/>
ロック解除する範囲内のバイト数。

### <a name="remarks"></a>解説

詳細については[、LockRange](#lockrange)メンバー関数の説明を参照してください。

> [!NOTE]
> この関数は、-derived`CMemFile`クラスでは使用できません。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]

## <a name="cfilewrite"></a><a name="write"></a>ファイル::書き込み

バッファーからオブジェクトに関連付けられたファイルにデータを`CFile`書き込みます。

```
virtual void Write(
    const void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>パラメーター

*lpBuf*<br/>
ファイルに書き込まれるデータを格納するユーザーが指定したバッファーへのポインター。

*nカウント*<br/>
バッファーから転送されるバイト数。 テキスト モード ファイルの場合、復帰線フィードのペアは 1 文字としてカウントされます。

### <a name="remarks"></a>解説

`Write`ディスク満杯条件を含むいくつかの条件に応答して例外をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#16](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_19.cpp)]

また[、CFile::CFile](#cfile)と[CFile::開くの](#open)例も参照してください。

## <a name="see-also"></a>関連項目

[MFC サンプル ドローCLI](../../overview/visual-cpp-samples.md)<br/>
[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラスを指定します。](../../mfc/reference/cstdiofile-class.md)<br/>
[CMemファイルクラス](../../mfc/reference/cmemfile-class.md)
