---
title: CArchiveException クラス
ms.date: 11/04/2016
f1_keywords:
- CArchiveException
- AFX/CArchiveException
- AFX/CArchiveException::CArchiveException
- AFX/CArchiveException::m_cause
- AFX/CArchiveException::m_strFileName
helpviewer_keywords:
- CArchiveException [MFC], CArchiveException
- CArchiveException [MFC], m_cause
- CArchiveException [MFC], m_strFileName
ms.assetid: da31a127-e86c-41d1-b0b6-bed0865b1b49
ms.openlocfilehash: ad2a9d8c5b4466a04b5a88fcce7679911bf1b81a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377014"
---
# <a name="carchiveexception-class"></a>CArchiveException クラス

シリアル化例外条件を表します。

## <a name="syntax"></a>構文

```
class CArchiveException : public CException
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[アーカイブ例外::Cアーカイブ例外](#carchiveexception)|`CArchiveException` オブジェクトを構築します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[アーカイブ例外::m_cause](#m_cause)|例外の原因を示します。|
|[アーカイブ例外::m_strFileName](#m_strfilename)|この例外条件のファイル名を指定します。|

## <a name="remarks"></a>解説

クラス`CArchiveException`には、例外の原因を示すパブリック データ メンバーが含まれています。

`CArchiveException`オブジェクトは[CArchive](../../mfc/reference/carchive-class.md)メンバー関数の内部で構築され、スローされます。 CATCH**式の**スコープ内でこれらのオブジェクトにアクセスできます。 原因コードは、オペレーティング システムから独立しています。 例外処理の詳細については、「[例外処理 (MFC)」](../../mfc/exception-handling-in-mfc.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CArchiveException`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="carchiveexceptioncarchiveexception"></a><a name="carchiveexception"></a>アーカイブ例外::Cアーカイブ例外

オブジェクトを`CArchiveException`構築し、*オブジェクトに原因*の値を格納します。

```
CArchiveException(
    int cause = CArchiveException::none,
    LPCTSTR lpszArchiveName = NULL);
```

### <a name="parameters"></a>パラメーター

*原因*<br/>
例外の理由を示す列挙型変数。 列挙子の一覧については[、m_cause](#m_cause)データ メンバーを参照してください。

*名前を変更します。*<br/>
例外の原因となっているオブジェクトの名前を`CArchive`含む文字列へのアクセスをポイントします。

### <a name="remarks"></a>解説

ヒープ上にオブジェクト`CArchiveException`を作成して自分でスローするか、グローバル関数[AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception)で処理させることができます。

このコンストラクターを直接使用しないでください。代わりに、グローバル関数`AfxThrowArchiveException`を呼び出します。

## <a name="carchiveexceptionm_cause"></a><a name="m_cause"></a>アーカイブ例外::m_cause

例外の原因を指定します。

```
int m_cause;
```

### <a name="remarks"></a>解説

このデータ メンバは、 **int**型のパブリック変数です。その値は`CArchiveException`列挙型によって定義されます。 列挙子とその意味は次のとおりです。

- `CArchiveException::none`エラーは発生しません。

- `CArchiveException::genericException`指定されていないエラーです。

- `CArchiveException::readOnly`読み込みのために開かれたアーカイブに書き込もうとしました。

- `CArchiveException::endOfFile`オブジェクトの読み取り中にファイルの末尾に到達しました。

- `CArchiveException::writeOnly`保存用に開かれたアーカイブから読み取ろうとしました。

- `CArchiveException::badIndex`無効なファイル形式です。

- `CArchiveException::badClass`オブジェクトを間違った型のオブジェクトに読み込もうとしました。

- `CArchiveException::badSchema`別のバージョンのクラスを持つオブジェクトを読み取ろうとしました。

    > [!NOTE]
    >  これらの `CArchiveException` 原因列挙子は、`CFileException` 原因列挙子とは異なります。

    > [!NOTE]
    > `CArchiveException::generic` は非推奨とされます。 代わりに `genericException` を使用してください **ジェネリック**がアプリケーションで使用され、/clr でビルドされた場合、構文エラーが解読しにくいことがあります。

## <a name="carchiveexceptionm_strfilename"></a><a name="m_strfilename"></a>アーカイブ例外::m_strFileName

この例外条件のファイル名を指定します。

```
CString m_strFileName;
```

## <a name="see-also"></a>関連項目

[クラスの例外](../../mfc/reference/cexception-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CArchive クラス](../../mfc/reference/carchive-class.md)<br/>
[AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception)<br/>
[例外処理](../../mfc/reference/exception-processing.md)
