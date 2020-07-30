---
title: CMemFile クラス
description: CMemFile クラスで使用できる関数について説明します。このクラスを使用して、メモリファイルを操作できます。
ms.date: 07/23/2020
f1_keywords:
- CMemFile
- AFX/CMemFile
- AFX/CMemFile::CMemFile
- AFX/CMemFile::Attach
- AFX/CMemFile::Detach
- AFX/CMemFile::Alloc
- AFX/CMemFile::Free
- AFX/CmemFile::GetBufferPtr
- AFX/CMemFile::GrowFile"
- AFX/CMemFile::Memcpy
- AFX/CMemFile::Realloc
helpviewer_keywords:
- CMemFile [MFC], CMemFile
- CMemFile [MFC], Attach
- CMemFile [MFC], Detach
- CMemFile [MFC], Alloc
- CMemFile [MFC], Free
- CMemFile [MFC], GetBufferPtr
- CMemFile [MFC], GrowFile
- CMemFile [MFC], Memcpy
- CMemFile [MFC], Realloc
ms.assetid: 20e86515-e465-4f73-b2ea-e49789d63165
ms.openlocfilehash: edd1d8b8d3979427602bdb61fc7647aec15d58b5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222941"
---
# <a name="cmemfile-class"></a>CMemFile クラス

メモリファイルをサポートする[CFile](../../mfc/reference/cfile-class.md)派生クラス。

## <a name="syntax"></a>構文

```
class CMemFile : public CFile
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|[説明]|
|----------|-----------------|
|[CMemFile:: CMemFile](#cmemfile)|メモリファイルオブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|[説明]|
|----------|-----------------|
|[CMemFile:: Attach](#attach)|メモリのブロックをにアタッチ `CMemFile` します。|
|[CMemFile::D etach](#detach)|からメモリブロックをデタッチし、 `CMemFile` デタッチされたメモリブロックへのポインターを返します。|
|[CMemFile:: GetBufferPtr](#getbufferptr)|メモリファイルをバッキングするメモリバッファーを取得または書き込みます。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|[説明]|
|----------|-----------------|
|[CMemFile:: Alloc](#alloc)|メモリ割り当て動作を変更するには、をオーバーライドします。|
|[CMemFile:: Free](#free)|メモリの解放動作を変更するには、をオーバーライドします。|
|[CMemFile:: GrowFile](#growfile)|ファイルを拡張するときの動作を変更するには、をオーバーライドします。|
|[CMemFile:: Memcpy](#memcpy)|ファイルの読み取りと書き込み時のメモリコピー動作を変更するには、をオーバーライドします。|
|[CMemFile:: Realloc](#realloc)|メモリ再割り当て動作を変更するには、をオーバーライドします。|

## <a name="remarks"></a>解説

これらのメモリファイルはディスクファイルのように動作しますが、ファイルはディスク上ではなく RAM に格納される点が異なります。 メモリファイルは、次の場合に役立ちます。

- 高速一時ストレージ
- 独立したプロセス間での生バイトの転送
- 独立したプロセス間でのシリアル化されたオブジェクトの転送

`CMemFile`オブジェクトは、独自のメモリを自動的に割り当てることができます。 または、Attach を呼び出して、オブジェクトに独自のメモリブロックをアタッチすることもでき `CMemFile` ます。 [Attach](#attach) どちらの場合も、メモリファイルを自動的に拡張するためのメモリは、が0でない場合、サイズの増加した単位で割り当てられ `nGrowBytes` `nGrowBytes` ます。

メモリブロックは、 `CMemFile` メモリが最初にオブジェクトによって割り当てられた場合は、オブジェクトの破棄時に自動的に削除されます `CMemFile` 。それ以外の場合は、オブジェクトにアタッチしたメモリの割り当てを解除します。

メモリブロックには、Detach を呼び出してオブジェクトからデタッチするときに指定されたポインターを使用してアクセスでき `CMemFile` ます。 [Detach](#detach)

の最も一般的な使用方法 `CMemFile` は、オブジェクトを作成 `CMemFile` し、 [CFile](../../mfc/reference/cfile-class.md)メンバー関数を呼び出すことによって使用することです。 を作成すると、 `CMemFile` 自動的に開きます。 [CFile:: Open](../../mfc/reference/cfile-class.md#open)は、ディスクファイルにのみ使用されます。 は `CMemFile` ディスクファイルを使用しないため、データメンバーは使用されません `CFile::m_hFile` 。

`CFile`メンバー関数[Duplicate](../../mfc/reference/cfile-class.md#duplicate)、 [LockRange](../../mfc/reference/cfile-class.md#lockrange)、および[UnlockRange](../../mfc/reference/cfile-class.md#unlockrange)は、に対しては実装されていません `CMemFile` 。 オブジェクトに対してこれらの関数を呼び出すと、 `CMemFile` [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)が得られます。

`CMemFile`では、ランタイムライブラリ関数[malloc](../../c-runtime-library/reference/malloc.md)、 [realloc](../../c-runtime-library/reference/realloc.md)、および[free](../../c-runtime-library/reference/free.md)を使用して、メモリの割り当て、再割り当て、および解放を行います。および組み込みの[memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)は、読み取り時および書き込み時にコピーメモリをブロックします。 この動作を変更する場合、またはでファイルを拡張するときの動作を変更する場合は `CMemFile` 、から独自のクラスを派生させ、 `CMemFile` 適切な関数をオーバーライドします。

の詳細については `CMemFile` 、「 [Mfc](../../mfc/files-in-mfc.md)および[メモリ管理 (mfc)](../../mfc/memory-management.md) 」の記事ファイルと、「*ランタイムライブラリリファレンス*」の「[ファイル処理](../../c-runtime-library/file-handling.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CMemFile`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx

## <a name="cmemfilealloc"></a><a name="alloc"></a>CMemFile:: Alloc

この関数は、メンバー関数によって呼び出され `CMemFile` ます。

```
virtual BYTE* Alloc(SIZE_T nBytes);
```

### <a name="parameters"></a>パラメーター

*nBytes*<br/>
割り当てられるメモリのバイト数。

### <a name="return-value"></a>戻り値

割り当てられたメモリブロックへのポインター。割り当てに失敗した場合は NULL。

### <a name="remarks"></a>解説

カスタムメモリ割り当てを実装するには、この関数をオーバーライドします。 この関数をオーバーライドする場合は、 [Free](#free)と[Realloc](#realloc)もオーバーライドすることをお勧めします。

既定の実装では、ランタイムライブラリ関数[malloc](../../c-runtime-library/reference/malloc.md)を使用してメモリを割り当てます。

## <a name="cmemfileattach"></a><a name="attach"></a>CMemFile:: Attach

メモリのブロックをにアタッチするには、この関数を呼び出し `CMemFile` ます。

```cpp
void Attach(
    BYTE* lpBuffer,
    UINT nBufferSize,
    UINT nGrowBytes = 0);
```

### <a name="parameters"></a>パラメーター

*lpBuffer*<br/>
アタッチされるバッファーへのポインター `CMemFile` 。

*nBufferSize*<br/>
バッファーのサイズをバイト単位で指定する整数です。

*nGrowBytes*<br/>
メモリ割り当ての増分値 (バイト単位)。

### <a name="remarks"></a>解説

これにより、はメモリ `CMemFile` のブロックをメモリファイルとして使用します。

*Ngrowbytes*が0の場合、 `CMemFile` ファイルの長さは*nbuffersize*に設定されます。 これは、にアタッチされる前のメモリブロック内のデータが、 `CMemFile` ファイルとして使用されることを意味します。 この方法で作成されたメモリファイルは拡張できません。

ファイルは拡張できないため、が `CMemFile` ファイルの拡張を試行しないように注意してください。 たとえば、 `CMemFile` [Cfile: write](../../mfc/reference/cfile-class.md#write)のオーバーライドを呼び出して、末尾を越えて書き込むか、 *nbuffersize*より長い長さで[cfile: SetLength](../../mfc/reference/cfile-class.md#setlength)を呼び出さないでください。

*Ngrowbytes*が0より大きい場合、 `CMemFile` はアタッチしたメモリブロックの内容を無視します。 のオーバーライドを使用して、最初からメモリファイルの内容を書き込む必要があり `CMemFile` `CFile::Write` ます。 ファイルの末尾を越えて書き込もうとした場合、またはのオーバーライドを呼び出してファイルを拡張しようとすると `CMemFile` `CFile::SetLength` 、 `CMemFile` は*ngrowbytes*単位でメモリの割り当てを拡張します。 に渡すメモリブロックが `Attach` [Alloc](#alloc)と互換性のあるメソッドで割り当てられていない場合、メモリ割り当ての増加は失敗します。 の既定の実装との互換性を確保するには、 `Alloc` ランタイムライブラリ関数[malloc](../../c-runtime-library/reference/malloc.md)または[calloc](../../c-runtime-library/reference/calloc.md)を使用してメモリを割り当てる必要があります。

## <a name="cmemfilecmemfile"></a><a name="cmemfile"></a>CMemFile:: CMemFile

最初のオーバーロードは、空のメモリファイルを開きます。

```
CMemFile(UINT nGrowBytes = 1024);

CMemFile(
    BYTE* lpBuffer,
    UINT nBufferSize,
    UINT nGrowBytes = 0);
```

### <a name="parameters"></a>パラメーター

*nGrowBytes*<br/>
メモリ割り当ての増分値 (バイト単位)。

*Lpbuffer*サイズ*Nbuffersize*の情報を受け取るバッファーへのポインター。

*nBufferSize*<br/>
ファイルバッファーのサイズをバイト単位で指定する整数です。

### <a name="remarks"></a>解説

ファイルはコンストラクターによって開かれます。 [CFile:: Open](../../mfc/reference/cfile-class.md#open)を呼び出さないでください。

2番目のオーバーロードは、最初のコンストラクターを使用した場合と同じように動作し、すぐに同じパラメーターを使用して[Attach](#attach)を呼び出します。 詳細については、`Attach` を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#36](../../atl-mfc-shared/reference/codesnippet/cpp/cmemfile-class_1.cpp)]

## <a name="cmemfiledetach"></a><a name="detach"></a>CMemFile::D etach

によって使用されているメモリブロックへのポインターを取得するには、この関数を呼び出し `CMemFile` ます。

```
BYTE* Detach();
```

### <a name="return-value"></a>戻り値

メモリファイルの内容を格納しているメモリブロックへのポインター。

### <a name="remarks"></a>解説

この関数を呼び出すと、も閉じら `CMemFile` れます。 `CMemFile` [Attach](#attach)を呼び出すことによって、メモリブロックをに再アタッチできます。 ファイルを再アタッチしてそのデータを使用する場合は、を呼び出す前に、 [CFile:: GetLength](../../mfc/reference/cfile-class.md#getlength)を呼び出して、ファイルの長さを取得する必要があり `Detach` ます。 メモリブロックをにアタッチし `CMemFile` てそのデータ (= = 0) を使用できるようにした場合 `nGrowBytes` 、メモリファイルを拡張することはできません。

## <a name="cmemfilefree"></a><a name="free"></a>CMemFile:: Free

この関数は、メンバー関数によって呼び出され `CMemFile` ます。

```
virtual void Free(BYTE* lpMem);
```

### <a name="parameters"></a>パラメーター

*lpMem*<br/>
割り当てを解除するメモリへのポインター。

### <a name="remarks"></a>解説

この関数をオーバーライドして、カスタムメモリ解放を実装します。 この関数をオーバーライドする場合は、 [Alloc](#alloc)と[Realloc](#realloc)もオーバーライドすることをお勧めします。

## <a name="cmemfilegetbufferptr"></a><a name="getbufferptr"></a>CMemFile:: GetBufferPtr

メモリファイルをバッキングするメモリバッファーを取得または書き込みます。

```cpp
virtual UINT GetBufferPtr(
    UINT nCommand,
    UINT nCount = 0,
    void** ppBufStart = NULL,
    void** ppBufMax = NULL
);
```

### <a name="parameters"></a>パラメーター

*N コマンド*<br/>
実行する[buffercommand](buffercommand-enumeration.md) (、、 `bufferCheck` `bufferCommit` `bufferRead` 、または `bufferWrite` )。

*nCount*<br/>
*N コマンド*に応じて、読み取り、書き込み、またはコミットするバッファー内のバイト数。 バッファーから読み取る場合は、-1 を指定して、現在の位置からファイルの末尾までのバッファーを返します。

*ppBufStart*<br/>
入出力バッファーの先頭。 `NULL` *N コマンド*がの場合は、にする必要があり `bufferCommit` ます。

*ppBufMax*<br/>
入出力バッファーの末尾。 N コマンドがの場合は、にする必要があり `NULL` `bufferCommit` ます。

### <a name="return-value"></a>戻り値

| *コマンド*値 | 戻り値 |
|--|--|
| `buffercheck` | 直接バッファリングがサポートされている場合は[Bufferdirect](buffercommand-enumeration.md)を返し、それ以外の場合は0を返します。 |
| `bufferCommit` | `0` を返します。 |
| `bufferRead` または `bufferWrite` | 返されたバッファー領域のバイト数を返します。 *ppBufStart*と*ppBufMax*は、読み取りと書き込みが可能なバッファーの先頭と末尾を指します。  |

### <a name="remarks"></a>解説

メモリバッファー () の現在の位置 `m_nPosition` は、 *n コマンド*に応じて次のように高度になります。

| *N コマンド* | バッファーの位置 |
|-|-|
| `bufferCommit` | 現在の位置は、コミットされたバッファーのサイズによって進めます。 |
| `bufferRead` | 現在の位置は、読み取りバッファーのサイズによって進めます。 |

## <a name="cmemfilegrowfile"></a><a name="growfile"></a>CMemFile:: GrowFile

この関数は、いくつかのメンバー関数によって呼び出され `CMemFile` ます。

```
virtual void GrowFile(SIZE_T dwNewLen);
```

### <a name="parameters"></a>パラメーター

*dwNewLen*<br/>
メモリファイルの新しいサイズ。

### <a name="remarks"></a>解説

がファイルをどのように拡張するかを変更する場合は、オーバーライドでき `CMemFile` ます。 既定の実装では、 [Realloc](#realloc)を呼び出して既存のブロック (またはメモリブロックを作成するための[Alloc](#alloc) ) を増やし、 `nGrowBytes` コンストラクターまたは[アタッチ](#attach)呼び出しで指定された値の倍数でメモリを割り当てます。

## <a name="cmemfilememcpy"></a><a name="memcpy"></a>CMemFile:: Memcpy

この関数は、 `CMemFile` メモリファイルとの間でデータを転送するための、 [cfile:: Read](../../mfc/reference/cfile-class.md#read)と[cfile:: Write](../../mfc/reference/cfile-class.md#write)のオーバーライドによって呼び出されます。

```
virtual BYTE* Memcpy(
    BYTE* lpMemTarget,
    const BYTE* lpMemSource,
    SIZE_T nBytes);
```

### <a name="parameters"></a>パラメーター

*lpMemTarget*<br/>
ソースメモリがコピーされるメモリブロックへのポインター。

*lpMemSource*<br/>
ソースメモリブロックへのポインター。

*nBytes*<br/>
コピー対象のバイト数。

### <a name="return-value"></a>戻り値

*Lpmemtarget*のコピー。

### <a name="remarks"></a>解説

これらのメモリのコピー方法を変更する場合は、この関数をオーバーライドし `CMemFile` ます。

## <a name="cmemfilerealloc"></a><a name="realloc"></a>CMemFile:: Realloc

この関数は、メンバー関数によって呼び出され `CMemFile` ます。

```
virtual BYTE* Realloc(
    BYTE* lpMem,
    SIZE_T nBytes);
```

### <a name="parameters"></a>パラメーター

*lpMem*<br/>
再割り当てするメモリブロックへのポインター。

*nBytes*<br/>
メモリブロックの新しいサイズ。

### <a name="return-value"></a>戻り値

再割り当てされた (または移動された可能性がある) メモリブロックへのポインター。または、再割り当てが失敗した場合は NULL。

### <a name="remarks"></a>解説

この関数をオーバーライドして、カスタムメモリ再割り当てを実装します。 この関数をオーバーライドする場合は、 [Alloc](#alloc)と[Free](#free)もオーバーライドすることをお勧めします。

## <a name="see-also"></a>関連項目

[CFile クラス](../../mfc/reference/cfile-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
