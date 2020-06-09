---
title: '例外処理 : 独自関数からの例外のスロー'
ms.date: 11/04/2016
helpviewer_keywords:
- throwing exceptions [MFC], from functions
- functions [MFC], throwing exceptions
- exceptions [MFC], throwing
ms.assetid: 492976e8-8804-4234-8e8f-30dffd0501be
ms.openlocfilehash: ebdfea18e6e8445dd734bf43fb6a4ecf422975e9
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622743"
---
# <a name="exceptions-throwing-exceptions-from-your-own-functions"></a>例外処理 : 独自関数からの例外のスロー

Mfc またはその他のライブラリの関数によってスローされた例外をキャッチするためだけに、MFC 例外処理パラダイムを使用することができます。 ライブラリコードによってスローされた例外をキャッチするだけでなく、例外的な状況に遭遇する可能性のある関数を記述する場合は、独自のコードから例外をスローすることができます。

例外がスローされると、現在の関数の実行は停止され、最も内側の例外フレームの**catch**ブロックに直接ジャンプします。 例外メカニズムは、関数からの通常の終了パスをバイパスします。 そのため、通常の終了時に削除されるメモリブロックを必ず削除してください。

#### <a name="to-throw-an-exception"></a>例外をスローするには

1. などの MFC ヘルパー関数のいずれかを使用し `AfxThrowMemoryException` ます。 これらの関数は、適切な型の事前割り当て済みの例外オブジェクトをスローします。

   次の例では、関数が2つのメモリブロックを割り当てようとし、いずれかの割り当てが失敗した場合に例外をスローします。

   [!code-cpp[NVC_MFCExceptions#17](codesnippet/cpp/exceptions-throwing-exceptions-from-your-own-functions_1.cpp)]

   最初の割り当てが失敗した場合は、単にメモリ例外をスローできます。 最初の割り当てが成功しても、2つ目の割り当てが失敗した場合は、例外をスローする前に最初の割り当てブロックを解放する必要があります。 両方の割り当てが成功した場合は、正常に続行して、関数を終了するときにブロックを解放できます。

     - または

1. 問題の状態を示すには、ユーザー定義の例外を使用します。 例外として、クラス全体であっても、任意の型の項目をスローすることができます。

   次の例では、wave デバイスでサウンドを再生しようとして、エラーが発生した場合に例外をスローします。

   [!code-cpp[NVC_MFCExceptions#18](codesnippet/cpp/exceptions-throwing-exceptions-from-your-own-functions_2.cpp)]

> [!NOTE]
> MFC の既定の例外処理は、 `CException` オブジェクト (および派生クラスのオブジェクト) へのポインターにのみ適用さ `CException` れます。 上記の例では、MFC の例外機構をバイパスしています。

## <a name="see-also"></a>関連項目

[例外処理](exception-handling-in-mfc.md)
