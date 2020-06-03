---
title: CMemファイルクラス
ms.date: 11/04/2016
f1_keywords:
- CMemFile
- AFX/CMemFile
- AFX/CMemFile::CMemFile
- AFX/CMemFile::Attach
- AFX/CMemFile::Detach
- AFX/CMemFile::Alloc
- AFX/CMemFile::Free
- AFX/CMemFile::GrowFile
- AFX/CMemFile::Memcpy
- AFX/CMemFile::Realloc
helpviewer_keywords:
- CMemFile [MFC], CMemFile
- CMemFile [MFC], Attach
- CMemFile [MFC], Detach
- CMemFile [MFC], Alloc
- CMemFile [MFC], Free
- CMemFile [MFC], GrowFile
- CMemFile [MFC], Memcpy
- CMemFile [MFC], Realloc
ms.assetid: 20e86515-e465-4f73-b2ea-e49789d63165
ms.openlocfilehash: 1bd88ad17bdb047de4c344ab96f3d9aecbe23c31
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752632"
---
# <a name="cmemfile-class"></a>CMemファイルクラス

メモリ ファイルをサポートする[CFile](../../mfc/reference/cfile-class.md)派生クラス。

## <a name="syntax"></a>構文

```
class CMemFile : public CFile
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMemファイル::CMemファイル](#cmemfile)|メモリ ファイル オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMemファイル::アタッチ](#attach)|メモリブロックを に接続します`CMemFile`。|
|[CMemFile::Dエタッハ](#detach)|メモリ ブロックをデタッチ`CMemFile`し、デタッチされたメモリ ブロックへのポインターを返します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CMemファイル::オロック](#alloc)|メモリ割り当ての動作を変更する場合にオーバーライドします。|
|[CMemファイル::無料](#free)|メモリの割り当て解除動作を変更する場合にオーバーライドします。|
|[CMemファイル::ファイルを成長させる](#growfile)|ファイルを拡張するときの動作を変更する場合にオーバーライドします。|
|[CMemFile::メムピー](#memcpy)|ファイルの読み取りおよび書き込み時のメモリ コピーの動作を変更する場合は、オーバーライドします。|
|[CMemFile::リアルロック](#realloc)|メモリの再割り当て動作を変更する場合にオーバーライドします。|

## <a name="remarks"></a>解説

これらのメモリ ファイルは、ディスクファイルではなく RAM に格納される点を除いて、ディスク ファイルのように動作します。 メモリ ファイルは、高速な一時記憶域、または独立したプロセス間で生のバイトまたはシリアル化されたオブジェクトを転送する場合に便利です。

`CMemFile`オブジェクトは、独自のメモリを自動的に割り当てることも[、Attach](#attach)`CMemFile`を呼び出して独自のメモリ ブロックをオブジェクトにアタッチすることもできます。 いずれの場合も、メモリ ファイルを自動的に拡張するためのメモリは、0 以外の`nGrowBytes`場合`nGrowBytes`は -サイズの増分で割り当てられます。

メモリブロックは、オブジェクトによって最初に`CMemFile`割り当てられた場合、オブジェクトの破棄時に自動的に`CMemFile`削除されます。それ以外の場合は、オブジェクトにアタッチしたメモリの割り当てを解除する必要があります。

Detach を呼び出すことで、オブジェクトからデタッチするときに指定されたポインター`CMemFile`を通じて[Detach](#detach)メモリ ブロックにアクセスできます。

最も一般的な`CMemFile`使用は`CMemFile`[、CFile](../../mfc/reference/cfile-class.md)メンバー関数を呼び出すことによってオブジェクトを作成し、それを使用することです。 自動的に作成すると`CMemFile`[、CFile::Open](../../mfc/reference/cfile-class.md#open)を呼び出すのではなく、ディスクファイルに対してのみ使用されます。 ディスク`CMemFile`ファイルを使用しないため、データ メンバー`CFile::m_hFile`は使用されません。

メンバー`CFile`関数[の複製](../../mfc/reference/cfile-class.md#duplicate)、[ロック範囲](../../mfc/reference/cfile-class.md#lockrange)、および[ロック範囲](../../mfc/reference/cfile-class.md#unlockrange)は、 には`CMemFile`実装されていません。 オブジェクトに対してこれらの関数を`CMemFile`呼び出すと、 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)が表示されます。

`CMemFile`は、ランタイム ライブラリ関数[malloc](../../c-runtime-library/reference/malloc.md)、 [realloc](../../c-runtime-library/reference/realloc.md)、[および free](../../c-runtime-library/reference/free.md)を使用して、メモリの割り当て、再割り当て、および割り当て解除を行います。読み書き時にコピーメモリをブロックする本質的[なmemcpy。](../../c-runtime-library/reference/memcpy-wmemcpy.md) ファイルが拡張されたとき`CMemFile`のこの動作や動作を変更する場合は、独自のクラスを派生`CMemFile`させ、適切な関数をオーバーライドします。

詳細`CMemFile`については、「MFC および[メモリ管理 (MFC)の](../../mfc/memory-management.md)[ファイル](../../mfc/files-in-mfc.md)」および「ランタイム ライブラリ リファレンス」の[「ファイルの処理](../../c-runtime-library/file-handling.md)」を*参照してください*。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CMemFile`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="cmemfilealloc"></a><a name="alloc"></a>CMemファイル::オロック

この関数は、メンバー`CMemFile`関数によって呼び出されます。

```
virtual BYTE* Alloc(SIZE_T nBytes);
```

### <a name="parameters"></a>パラメーター

*Nbytes*<br/>
割り当てるメモリのバイト数。

### <a name="return-value"></a>戻り値

割り当てられたメモリ ブロックへのポインター。

### <a name="remarks"></a>解説

カスタム メモリ割り当てを実装するには、この関数をオーバーライドします。 この関数をオーバーライドする場合は[、Free](#free)と[Realloc](#realloc)もオーバーライドする必要があります。

既定の実装では、ランタイム ライブラリ関数[malloc](../../c-runtime-library/reference/malloc.md)を使用してメモリを割り当てます。

## <a name="cmemfileattach"></a><a name="attach"></a>CMemファイル::アタッチ

メモリ ブロックを にアタッチします`CMemFile`。

```cpp
void Attach(
    BYTE* lpBuffer,
    UINT nBufferSize,
    UINT nGrowBytes = 0);
```

### <a name="parameters"></a>パラメーター

*バッファバッファ*<br/>
にアタッチするバッファーへの`CMemFile`ポインター。

*バッファサイズ*<br/>
バッファーのサイズをバイト単位で指定する整数。

*nグローバイト*<br/>
メモリ割り当てのインクリメント (バイト単位)。

### <a name="remarks"></a>解説

これにより`CMemFile`、メモリ ブロックがメモリ ファイルとして使用されます。

*nGrowBytes が*0`CMemFile`の場合は、ファイルの長さを*nBufferSize*に設定します。 つまり、メモリ ブロックのデータがアタッチされる前の`CMemFile`データがファイルとして使用されます。 この方法で作成されたメモリ ファイルは、サイズを大きくすることはできません。

ファイルを拡張することはできないので、ファイルの拡張`CMemFile`を試みないように注意してください。 たとえば[、CFile:Write](../../mfc/reference/cfile-class.md#write)の`CMemFile`オーバーライドを呼び出して末尾を過ぎて書き込んだり *、nBufferSize*より長い長さの[CFile:SetLength を](../../mfc/reference/cfile-class.md#setlength)呼び出さないでください。

*nGrowBytes*が 0 より`CMemFile`大きい場合、アタッチしたメモリ ブロックの内容は無視されます。 のオーバーライドを使用して、メモリ ファイルの内容を`CMemFile`最初から書き込む`CFile::Write`必要があります。 ファイルの末尾を過ぎて書き込もう`CMemFile`とするか`CFile::SetLength`、 の`CMemFile`オーバーライドを呼び出してファイルを拡張すると、メモリの割り当てが*nGrowBytes*の増分で増加します。 渡すメモリ ブロックが[Alloc](#alloc)と互換性のある`Attach`メソッドと割り当てられていない場合、メモリ割り当ての増加は失敗します。 の既定の`Alloc`実装と互換性を持つには、ランタイム ライブラリ関数 malloc または[calloc](../../c-runtime-library/reference/malloc.md) [calloc](../../c-runtime-library/reference/calloc.md)を使用してメモリを割り当てる必要があります。

## <a name="cmemfilecmemfile"></a><a name="cmemfile"></a>CMemファイル::CMemファイル

最初のオーバーロードは空のメモリ ファイルを開きます。

```
CMemFile(UINT nGrowBytes = 1024);

CMemFile(
    BYTE* lpBuffer,
    UINT nBufferSize,
    UINT nGrowBytes = 0);
```

### <a name="parameters"></a>パラメーター

*nグローバイト*<br/>
メモリ割り当てのインクリメント (バイト単位)。

サイズの情報を受け取るバッファーへのポインターを*lpBuffe*r*を lBufferSize*。

*バッファサイズ*<br/>
ファイル バッファーのサイズをバイト単位で指定する整数。

### <a name="remarks"></a>解説

ファイルはコンストラクターによって開かれるので[、CFile::Open](../../mfc/reference/cfile-class.md#open)を呼び出してはならないことに注意してください。

2 番目のオーバーロードは、最初のコンストラクターを使用し、すぐに同じパラメーターを使用して[Attach と](#attach)呼ぶ場合と同じように動作します。 詳細については、`Attach` を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#36](../../atl-mfc-shared/reference/codesnippet/cpp/cmemfile-class_1.cpp)]

## <a name="cmemfiledetach"></a><a name="detach"></a>CMemFile::Dエタッハ

によって`CMemFile`使用されているメモリ ブロックへのポインターを取得します。

```
BYTE* Detach();
```

### <a name="return-value"></a>戻り値

メモリ ファイルの内容を格納するメモリ ブロックへのポインター。

### <a name="remarks"></a>解説

この関数を呼び出すと`CMemFile`、 も閉じます。 Attach を呼び出すことで、`CMemFile`メモリ[Attach](#attach)ブロックをに再接続できます。 ファイルを再アタッチしてファイル内のデータを使用する場合は[、CFile::GetLength](../../mfc/reference/cfile-class.md#getlength)を呼び出して、ファイルの長さを取得`Detach`してから呼び出す必要があります。 メモリブロックをアタッチして`CMemFile`データ(==0)`nGrowBytes`を使用すると、メモリファイルを拡張することはできません。

## <a name="cmemfilefree"></a><a name="free"></a>CMemファイル::無料

この関数は、メンバー`CMemFile`関数によって呼び出されます。

```
virtual void Free(BYTE* lpMem);
```

### <a name="parameters"></a>パラメーター

*lpMem*<br/>
割り当てを解除するメモリへのポインター。

### <a name="remarks"></a>解説

カスタム メモリの割り当て解除を実装するには、この関数をオーバーライドします。 この関数をオーバーライドする場合は[、Alloc](#alloc)と[Realloc](#realloc)もオーバーライドする必要があります。

## <a name="cmemfilegrowfile"></a><a name="growfile"></a>CMemファイル::ファイルを成長させる

この関数は、いくつかのメンバー関数によって`CMemFile`呼び出されます。

```
virtual void GrowFile(SIZE_T dwNewLen);
```

### <a name="parameters"></a>パラメーター

*ドニューレン*<br/>
メモリ ファイルの新しいサイズ。

### <a name="remarks"></a>解説

ファイルの拡大方法`CMemFile`を変更する場合は、このファイルをオーバーライドできます。 既定の実装では[Realloc](#realloc)を呼び出して既存のブロック (または、メモリ ブロックを作成する[場合は Alloc)](#alloc)を拡張し、コンストラクターまたは`nGrowBytes`[Attach](#attach)呼び出しで指定された値の倍数のメモリを割り当てる。

## <a name="cmemfilememcpy"></a><a name="memcpy"></a>CMemFile::メムピー

この関数は、メモリ`CMemFile`ファイルとの間でデータを転送する[CFile::Read](../../mfc/reference/cfile-class.md#read)と[CFile::書き込みの](../../mfc/reference/cfile-class.md#write)オーバーライドによって呼び出されます。

```
virtual BYTE* Memcpy(
    BYTE* lpMemTarget,
    const BYTE* lpMemSource,
    SIZE_T nBytes);
```

### <a name="parameters"></a>パラメーター

*ターゲットを指定します。*<br/>
ソース メモリのコピー先のメモリ ブロックへのポインター。

*lpMemソース*<br/>
ソース メモリ ブロックへのポインター。

*Nbytes*<br/>
コピー対象のバイト数。

### <a name="return-value"></a>戻り値

*lpMemTarget*のコピー。

### <a name="remarks"></a>解説

これらのメモリ コピーの方法を変更する場合は`CMemFile`、この関数をオーバーライドします。

## <a name="cmemfilerealloc"></a><a name="realloc"></a>CMemFile::リアルロック

この関数は、メンバー`CMemFile`関数によって呼び出されます。

```
virtual BYTE* Realloc(
    BYTE* lpMem,
    SIZE_T nBytes);
```

### <a name="parameters"></a>パラメーター

*lpMem*<br/>
再割り当てされるメモリ ブロックへのポインター。

*Nbytes*<br/>
メモリ ブロックの新しいサイズ。

### <a name="return-value"></a>戻り値

再割り当て (および移動された可能性のある) メモリ ブロックへのポインター。

### <a name="remarks"></a>解説

カスタム メモリの再割り当てを実装するには、この関数をオーバーライドします。 この関数をオーバーライドする場合は[、Alloc](#alloc)と[Free](#free)もオーバーライドする必要があります。

## <a name="see-also"></a>関連項目

[CFile クラス](../../mfc/reference/cfile-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
