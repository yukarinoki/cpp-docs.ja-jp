---
title: CString の使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/18/2018
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CString objects, C++ string manipulation
- CString objects, reference counting
- CString class (Visual C++)
ms.assetid: ed018aaf-8b10-46f9-828c-f9c092dc7609
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5759c8a0aaa628d612010cb7d04690a3d3bfa54f
ms.sourcegitcommit: d06966efce25c0e66286c8047726ffe743ea6be0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238722"
---
# <a name="using-cstring"></a>CString の使用
このセクションのトピックでは、`CString` を使用したプログラミング方法について説明します。 に関するリファレンス ドキュメント、`CString`クラス、ドキュメントを参照して[CStringT](../atl-mfc-shared/reference/cstringt-class.md)です。  
  
 `CString` を使用するには、`atlstr.h` ヘッダーをインクルードします。  
  
 `CString`、 `CStringA`、および`CStringW`クラスと呼ばれるクラス テンプレートの特殊化は、 [CStringT](../atl-mfc-shared/reference/cstringt-class.md)サポートされる文字データの種類に基づきます。  
  
 `CStringW` オブジェクトには `wchar_t` 型が格納され、Unicode 文字列がサポートされます。 `CStringA` オブジェクトには `char` 型が格納され、1 バイト文字列とマルチバイト (MBCS) 文字列がサポートされます。 `CString` オブジェクトでは、コンパイル時に `char` シンボルと `wchar_t` シンボルのどちらが定義されているかに従って、`MBCS` 型または `UNICODE` 型のいずれかがサポートされます。  
  
 `CString` オブジェクトは、`CStringData` オブジェクトの文字データを保持します。 `CString` 受け付ける`null`-C スタイルの文字列を終了します。 `CString` パフォーマンスを向上させることが、文字列の長さも保持トラック、 `null` LPCWSTR への変換をサポートするために格納されている文字データの文字です。 `CString` C スタイルの文字列をエクスポートする際に、null 終端文字が含まれます。 挿入することができます、`null`内の他の場所で、 `CString`、予期しない結果が生じる。  
  
 文字列クラス `CAtlString`、`CAtlStringA`、および `CAtlStringW` は、CRT サポートがある場合もない場合も、MFC ライブラリにリンクせずに使用できます。  
  
 `CString` は、ネイティブ プロジェクトで使用されます。 マネージ コード (C++/CLI) プロジェクトの場合は、`System::String` を使用します。  
  
 `CString`、`CStringA`、または `CStringW` で現在提供されているよりも多くの機能を追加するには、追加機能を含む `CStringT` のサブクラスを作成する必要があります。  
  
 次のコードは、`CString` を作成して標準出力に表示する方法を示しています。  
  
```cpp  
#include <atlstr.h>  
  
int main() {  
    CString aCString = CString(_T("A string"));  
    _tprintf(_T("%s"), (LPCTSTR) aCString);  
}  
```  
  
## <a name="in-this-section"></a>このセクションの内容  
 [CString の基本操作](../atl-mfc-shared/basic-cstring-operations.md)  
 C リテラル文字列からのオブジェクトの作成、`CString` 内の個々の文字へのアクセス、2 つのオブジェクトの連結、`CString` オブジェクトの比較など、`CString` の基本操作について説明します。  
  
 [文字列データ管理](../atl-mfc-shared/string-data-management.md)  
 `CString` での Unicode と MBCS の使用について説明します。  
  
 [CString セマンティクス](../atl-mfc-shared/cstring-semantics.md)  
 `CString` オブジェクトの使用方法について説明します。  
  
 [C スタイルの文字列に関連する CString の操作方法](../atl-mfc-shared/cstring-operations-relating-to-c-style-strings.md)  
 C スタイルの null で終わる文字列のように `CString` オブジェクトの内容を操作する方法について説明します。  
  
 [BSTR 用のメモリの割り当てと解放](../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md)  
 `BSTR` と COM オブジェクトのメモリの使用方法について説明します。  
  
 [CString の例外の後処理](../atl-mfc-shared/cstring-exception-cleanup.md)  
 MFC 3.0 以降で明示的な後処理が不要になったことについて説明します。  
  
 [CString 引数の渡し方](../atl-mfc-shared/cstring-argument-passing.md)  
 CString オブジェクトを関数に渡す方法と関数から `CString` オブジェクトを返す方法について説明します。  
  
 [Unicode とマルチバイト文字セット (MBCS: Multibyte Character Set) のサポート](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)  
 MFC で Unicode と MBCS をサポートできるようにする方法について説明します。  
  
## <a name="reference"></a>参照  
 [CStringT](../atl-mfc-shared/reference/cstringt-class.md)  
 `CStringT` クラスに関するリファレンス情報を提供します。  
  
 [CSimpleStringT クラス](../atl-mfc-shared/reference/csimplestringt-class.md)  
 `CSimpleStringT` クラスに関するリファレンス情報を提供します。  
  
## <a name="related-sections"></a>関連項目  
 [文字列 (ATL と MFC)](../atl-mfc-shared/strings-atl-mfc.md)  
 文字列データを管理する複数の方法について説明したトピックへのリンクが含まれています。  
  
 [文字列 (ATL と MFC)](../atl-mfc-shared/strings-atl-mfc.md)

