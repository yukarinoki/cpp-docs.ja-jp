---
title: CSharedFile クラス
ms.date: 11/04/2016
f1_keywords:
- CSharedFile
- AFXADV/CSharedFile
- AFXADV/CSharedFile::CSharedFile
- AFXADV/CSharedFile::Detach
- AFXADV/CSharedFile::SetHandle
helpviewer_keywords:
- CSharedFile [MFC], CSharedFile
- CSharedFile [MFC], Detach
- CSharedFile [MFC], SetHandle
ms.assetid: 5d000422-9ede-4318-a8c9-f7412b674f39
ms.openlocfilehash: e6a713ac9d9e906ec204d4a52b43ed51c08fd99c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318428"
---
# <a name="csharedfile-class"></a>CSharedFile クラス

共有メモリ ファイルをサポートする[CMemFile](../../mfc/reference/cmemfile-class.md)派生クラス。

## <a name="syntax"></a>構文

```
class CSharedFile : public CMemFile
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ファイルを共有します。](#csharedfile)|`CSharedFile` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ファイル::Dエタッハ](#detach)|共有メモリ ファイルを閉じ、そのメモリ ブロックのハンドルを返します。|
|[ファイルを共有します。](#sethandle)|共有メモリ ファイルをメモリ ブロックにアタッチします。|

## <a name="remarks"></a>解説

メモリファイルはディスクファイルのように動作します。 違いは、メモリファイルはディスクではなくRAMに格納される点です。 メモリ ファイルは、高速な一時記憶域、または独立したプロセス間で生のバイトまたはシリアル化されたオブジェクトを転送する場合に便利です。

共有メモリ ファイルは、そのメモリ内の他のメモリ ファイルとは異なり、そのメモリは[GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc) Windows 関数で割り当てられます。 クラス`CSharedFile`はグローバルに割り当てられたメモリ ブロック (を使用`GlobalAlloc`して作成) にデータを格納し、このメモリ ブロックは DDE、クリップボード、または他の OLE/COM`IDataObject`の統一されたデータ転送操作を使用して共有できます。

`GlobalAlloc`[は、malloc](../../c-runtime-library/reference/malloc.md)によって返されるポインターなどのメモリへのポインターではなく、HGLOBAL ハンドルを返します。 HGLOBAL ハンドルは、特定のアプリケーションで必要とされます。 たとえば、クリップボードにデータを格納するには、HGLOBAL ハンドルが必要です。

`CSharedFile`メモリマップファイルを使用せず、データをプロセス間で直接共有することはできません。

`CSharedFile`オブジェクトは、自動的に独自のメモリを割り当てることができます。 または[、CSharedFile::SetHandle](#sethandle)を`CSharedFile`呼び出すことによって、独自のメモリ ブロックをオブジェクトにアタッチできます。 いずれの場合も、メモリ ファイルを自動的に拡張するためのメモリは、0 でない場合`nGrowBytes``nGrowBytes`は -サイズの増分で割り当てられます。

詳細については、『ランタイム ライブラリ リファレンス[』の「MFC ファイル](../../mfc/files-in-mfc.md)と[ファイル処理](../../c-runtime-library/file-handling.md)」を*参照してください*。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CMemFile](../../mfc/reference/cmemfile-class.md)

`CSharedFile`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxadv.h

## <a name="csharedfilecsharedfile"></a><a name="csharedfile"></a>ファイルを共有します。

オブジェクトを`CSharedFile`構築し、そのオブジェクトにメモリを割り当てます。

```
CSharedFile(
    UINT nAllocFlags = GMEM_DDESHARE | GMEM_MOVEABLE,
    UINT nGrowBytes = 4096);
```

### <a name="parameters"></a>パラメーター

*フラグ*<br/>
メモリの割り当て方法を示すフラグ。 有効なフラグ値のリストについては[、GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc)を参照してください。

*nグローバイト*<br/>
メモリ割り当てのインクリメント (バイト単位)。

## <a name="csharedfiledetach"></a><a name="detach"></a>ファイル::Dエタッハ

メモリ ファイルを閉じ、メモリ ブロックからデタッチします。

```
HGLOBAL Detach();
```

### <a name="return-value"></a>戻り値

メモリ ファイルの内容を格納するメモリ ブロックのハンドル。

### <a name="remarks"></a>解説

**を**呼び出すことによって、再び開くことができます[。](#sethandle)

## <a name="csharedfilesethandle"></a><a name="sethandle"></a>ファイルを共有します。

`CSharedFile`オブジェクトにグローバル メモリのブロックをアタッチします。

```
void SetHandle(
    HGLOBAL hGlobalMemory,
    BOOL bAllowGrow = TRUE);
```

### <a name="parameters"></a>パラメーター

*を大きくるメモリ*<br/>
に接続するグローバル メモリへのハンドル`CSharedFile`。

*成長を許可する*<br/>
メモリ ブロックの拡張を許可するかどうかを指定します。

### <a name="remarks"></a>解説

*bAllowGrow*が 0 以外の場合、メモリ ブロックのサイズよりも多くのバイトをファイルに書き込もうとした場合など、必要に応じてメモリ ブロックのサイズが増加します。

## <a name="see-also"></a>関連項目

[CMemファイルクラス](../../mfc/reference/cmemfile-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CMemファイルクラス](../../mfc/reference/cmemfile-class.md)
