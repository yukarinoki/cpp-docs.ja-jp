---
title: ファイルを開く
ms.date: 11/04/2016
helpviewer_keywords:
- Open member functions [MFC]
- CFile class [MFC], variable
- opening files, in MFC
- Open calls [MFC]
- Open method, CFile class [MFC]
- examples [MFC], opening files
- opening files, handling exceptions
- exception handling [MFC], when opening files
- files [MFC], opening
- file objects [MFC]
- MFC, file operations
- opening files [MFC]
- exception handling [MFC], opening files
ms.assetid: a991b8ec-b04a-4766-b47e-7485b5dd0b01
ms.openlocfilehash: 73407eba802b7640e880b821144954fa6442f177
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622165"
---
# <a name="opening-files"></a>ファイルを開く

MFC では、ファイルを開くための最も一般的な方法は、2段階のプロセスです。

#### <a name="to-open-a-file"></a>ファイルを開くには

1. パスまたはアクセス許可フラグを指定せずに、ファイルオブジェクトを作成します。

   通常、ファイルオブジェクトを作成するには、スタックフレームで[CFile](reference/cfile-class.md)変数を宣言します。

1. ファイルオブジェクトの[Open](reference/cfile-class.md#open)メンバー関数を呼び出して、パスとアクセス許可フラグを指定します。

   の戻り値は、 `Open` ファイルが正常に開かれた場合は0以外の値になり、指定されたファイルを開くことができなかった場合は0になります。 この `Open` メンバー関数は、次のようにプロトタイプが宣言されています。

   `virtual BOOL Open( LPCTSTR lpszFileName, UINT nOpenFlags, CFileException* pError = NULL );`

   Open フラグは、ファイルに必要なアクセス許可 (読み取り専用など) を指定します。 使用可能なフラグ値は、クラス内で列挙定数として定義されているの `CFile` で、では "" として修飾され `CFile::` `CFile::modeRead` ます。 ファイルを `CFile::modeCreate` 作成する場合は、フラグを使用します。

次の例では、読み取り/書き込みアクセス許可を持つ新しいファイルを作成する方法を示しています (同じパスの前のファイルを置き換えます)。

[!code-cpp[NVC_MFCFiles#1](../atl-mfc-shared/reference/codesnippet/cpp/opening-files_1.cpp)]

> [!NOTE]
> この例では、ファイルを作成して開きます。 問題が発生した場合、 `Open` `CFileException` 次に示すように、呼び出しは最後のパラメーターでオブジェクトを返すことができます。 トレースマクロは、エラーの原因を示すファイル名とコードの両方を出力します。 `AfxThrowFileException`より詳細なエラー報告が必要な場合は、関数を呼び出すことができます。

## <a name="see-also"></a>関連項目

[CFile クラス](reference/cfile-class.md)<br/>
[CFile:: Open](reference/cfile-class.md#open)<br/>
[[ファイル]](files-in-mfc.md)
