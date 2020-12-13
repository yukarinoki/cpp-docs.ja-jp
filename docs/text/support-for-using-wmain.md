---
description: 詳細については、「wmain の使用のサポート」を参照してください。
title: wmain の使用
ms.date: 11/04/2016
f1_keywords:
- wWinMain
helpviewer_keywords:
- wide characters [C++], wmain function
- wWinMain function
- wmain function
ms.assetid: 41213c41-668c-40a4-8a1e-77d9eded720d
ms.openlocfilehash: b6a954ab62c9bc675bd2b71275d615b3ee4c1376
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335739"
---
# <a name="support-for-using-wmain"></a>wmain の使用

Visual C++ は、 **wmain** 関数を定義し、Unicode アプリケーションにワイド文字引数を渡すことをサポートしています。 **Wmain** に対して仮パラメーターを宣言するには、のような形式を使用し `main` ます。 さらに、ワイド文字の引数と、必要であればワイド文字環境ポインターもプログラムに渡すことができます。 **wmain** の引数 `argv` と `envp` の型は `wchar_t*` です。 次に例を示します。

```cpp
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )
```

> [!NOTE]
> MFC Unicode アプリケーションは `wWinMain` 、エントリポイントとしてを使用します。 この場合、 `CWinApp::m_lpCmdLine` は Unicode 文字列です。 必ず `wWinMainCRTStartup` [/entry](../build/reference/entry-entry-point-symbol.md) リンカーオプションを使用して設定してください。

プログラムが **main** 関数を使用している場合、マルチバイト文字環境は、プログラムの起動時にランタイム ライブラリが作成します。 マルチバイト文字環境で使われるワイド文字のコピーは、必要に応じて作成されます (たとえば、`_wgetenv` 関数や `_wputenv` 関数が呼び出されたとき)。 を最初に呼び出す `_wputenv` とき、または MBCS 環境が既に存在する場合にを最初に呼び出す `_wgetenv` ときに、対応するワイド文字の文字列環境が作成されます。 次に、グローバル変数 `_wenviron` (グローバル変数のワイド文字バージョン) によって環境がポイントされ `_environ` ます。 この時点で、2つの環境のコピー (MBCS および Unicode) が同時に存在し、プログラムの有効期間中はランタイムシステムによって保持されます。

プログラムが **wmain** 関数を使っている場合は、ワイド文字環境がプログラムの起動時に作成され、また `_wenviron` グローバル変数によって環境のアドレスが示されます。 MBCS (ASCII) 環境は、またはの最初の呼び出しで作成され、 `_putenv` `getenv` グローバル変数によってポイントされ `_environ` ます。

## <a name="see-also"></a>関連項目

[Unicode のサポート](../text/support-for-unicode.md)<br/>
[Unicode プログラミングの概要](../text/unicode-programming-summary.md)<br/>
[WinMain 関数](/windows/win32/api/winbase/nf-winbase-winmain)
