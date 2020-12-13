---
description: '詳細情報: CSharedFile クラス'
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
ms.openlocfilehash: 0eb2f76bdfa9e10c660f405e225698289b506014
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342832"
---
# <a name="csharedfile-class"></a>CSharedFile クラス

共有メモリファイルをサポートする [CMemFile](../../mfc/reference/cmemfile-class.md)の派生クラス。

## <a name="syntax"></a>構文

```
class CSharedFile : public CMemFile
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CSharedFile:: CSharedFile](#csharedfile)|`CSharedFile` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSharedFile::D etach。](#detach)|共有メモリファイルを閉じ、そのメモリブロックのハンドルを返します。|
|[CSharedFile:: SetHandle](#sethandle)|共有メモリファイルをメモリブロックにアタッチします。|

## <a name="remarks"></a>解説

メモリファイルは、ディスクファイルのように動作します。 違いは、メモリファイルがディスク上ではなく RAM に格納されていることです。 メモリファイルは、高速一時ストレージ、または生バイトまたはシリアル化されたオブジェクトを独立したプロセス間で転送する場合に役立ちます。

共有メモリファイルは、そのメモリ内の他のメモリファイルとは異なり、 [GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc) Windows 関数で割り当てられます。 クラスは、 `CSharedFile` を使用して作成されたグローバルに割り当てられたメモリブロックにデータを格納 `GlobalAlloc` します。このメモリブロックは、を使用するなど、DDE、クリップボード、またはその他の OLE/COM の一様なデータ転送操作を使用して共有でき `IDataObject` ます。

`GlobalAlloc`[malloc](../../c-runtime-library/reference/malloc.md)によって返されたポインターなど、メモリへのポインターではなく、HGLOBAL ハンドルを返します。 特定のアプリケーションでは、HGLOBAL ハンドルが必要です。 たとえば、クリップボードにデータを格納するには、HGLOBAL ハンドルが必要です。

`CSharedFile` では、メモリマップトファイルを使用せず、プロセス間でデータを直接共有することはできません。

`CSharedFile` オブジェクトは、独自のメモリを自動的に割り当てることができます。 または、 `CSharedFile` [Csharedfile:: SetHandle](#sethandle)を呼び出して、オブジェクトに独自のメモリブロックをアタッチすることもできます。 どちらの場合も、メモリファイルを自動的に拡張するためのメモリは、が0でない場合、サイズの増加した単位で割り当てられ `nGrowBytes` `nGrowBytes` ます。

詳細については、「 [MFC のファイル](../../mfc/files-in-mfc.md)」と「*ランタイムライブラリリファレンス*」の「[ファイル処理](../../c-runtime-library/file-handling.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CMemFile](../../mfc/reference/cmemfile-class.md)

`CSharedFile`

## <a name="requirements"></a>要件

**ヘッダー:** afxadv

## <a name="csharedfilecsharedfile"></a><a name="csharedfile"></a> CSharedFile:: CSharedFile

オブジェクトを構築 `CSharedFile` し、そのオブジェクトにメモリを割り当てます。

```
CSharedFile(
    UINT nAllocFlags = GMEM_DDESHARE | GMEM_MOVEABLE,
    UINT nGrowBytes = 4096);
```

### <a name="parameters"></a>パラメーター

*nAllocFlags*<br/>
メモリを割り当てる方法を示すフラグ。 有効なフラグ値の一覧については、「 [GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc) 」を参照してください。

*nGrowBytes*<br/>
メモリ割り当ての増分値 (バイト単位)。

## <a name="csharedfiledetach"></a><a name="detach"></a> CSharedFile::D etach。

メモリファイルを閉じてメモリブロックからデタッチするには、この関数を呼び出します。

```
HGLOBAL Detach();
```

### <a name="return-value"></a>戻り値

メモリファイルの内容を格納しているメモリブロックのハンドル。

### <a name="remarks"></a>解説

**Detach** によって返されたハンドルを使用して [SetHandle](#sethandle)を呼び出すことで、再度開くことができます。

## <a name="csharedfilesethandle"></a><a name="sethandle"></a> CSharedFile:: SetHandle

グローバルメモリのブロックをオブジェクトにアタッチするには、この関数を呼び出し `CSharedFile` ます。

```cpp
void SetHandle(
    HGLOBAL hGlobalMemory,
    BOOL bAllowGrow = TRUE);
```

### <a name="parameters"></a>パラメーター

*hGlobalMemory*<br/>
にアタッチするグローバルメモリへのハンドル `CSharedFile` 。

*bAllowGrow*<br/>
メモリブロックの拡張を許可するかどうかを指定します。

### <a name="remarks"></a>解説

*Ballowgrow* が0以外の場合は、メモリブロックのサイズよりも多くのバイトをファイルに書き込もうとするなど、必要に応じてメモリブロックのサイズが増加します。

## <a name="see-also"></a>関連項目

[CMemFile クラス](../../mfc/reference/cmemfile-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CMemFile クラス](../../mfc/reference/cmemfile-class.md)
