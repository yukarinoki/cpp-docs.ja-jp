---
title: C ランタイム エラー R6035
ms.date: 11/04/2016
f1_keywords:
- R6035
helpviewer_keywords:
- R6035
ms.assetid: f8fb50b8-18bf-4258-b96a-b0a9de468d16
ms.openlocfilehash: 7c497347689bcfc5528280bd22aa5183d5fafd61
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197005"
---
# <a name="c-runtime-error-r6035"></a>C ランタイム エラー R6035

Microsoft Visual C++ ランタイム ライブラリ、エラー R6035 - あるグローバル セキュリティ クッキーに依存している関数がアクティブになっている間に、このアプリケーション内のモジュールが、そのモジュールに所属するそのセキュリティ クッキーを初期化しました。  __security_init_cookie を既に呼び出しました。

グローバルセキュリティ cookie を初めて使用する前に、 [__security_init_cookie](../../c-runtime-library/reference/security-init-cookie.md)を呼び出す必要があります。

グローバルセキュリティ cookie は、 [/gs (バッファーセキュリティチェック)](../../build/reference/gs-buffer-security-check.md)を使用してコンパイルされたコードと、構造化例外処理を使用するコードでバッファーオーバーランによって保護されます。 基本的に、オーバーランから保護された関数を呼び出すとクッキーはスタックに配置され、関数の終了時に、スタックの値がグローバルなクッキーと比較されます。 違いが発見された場合は、バッファー オーバーランが発生したことを意味し、プログラムは直ちに終了します。

エラー R6035 は、保護された関数の呼び出し後に `__security_init_cookie` が呼び出されたことを示します。 実行を継続すると、スタック上のクッキーがグローバルなクッキーと一致しなくなるため、実際には発生していないバッファー オーバーランが検出されます。

次の DLL の例を考えます。 DLL のエントリポイントは、リンカー [/entry (エントリポイントシンボル)](../../build/reference/entry-entry-point-symbol.md)オプションを使用して dllentrypoint に設定されます。 これにより、通常はグローバル セキュリティ クッキーを初期化する CRT の初期化が省略されるため、DLL 自体で `__security_init_cookie` を呼び出す必要があります。

```
// Wrong way to call __security_init_cookie
DllEntryPoint(...) {
   DllInitialize();
   ...
   __try {
      ...
   } __except()... {
      ...
   }
}

void DllInitialize() {
   __security_init_cookie();
}
```

この例では、エラー R6035 が生成されます。これは、DllEntryPoint が構造化例外処理を使用するため、バッファー オーバーランの検出にセキュリティ クッキーを使用するからです。 DllInitialize が呼び出されるときには、グローバル セキュリティ クッキーは既にスタックに配置されています。

正しい方法については、次の例で説明します。

```
// Correct way to call __security_init_cookie
DllEntryPoint(...) {
   __security_init_cookie();
   DllEntryHelper();
}

void DllEntryHelper() {
   ...
   __try {
      ...
   } __except()... {
      ...
   }
}
```

この例では、DllEntryPoint はバッファー オーバーランに対して保護されていない (ローカルの文字列バッファーを含まず、構造化例外処理を使用しない) ため、`__security_init_cookie` を安全に呼び出すことができます。 その後、保護されているヘルパー関数を呼び出します。

> [!NOTE]
>  R6035 エラー メッセージが生成されるのは、x86 のデバッグ CRT、構造化例外処理の場合のみです。しかし、すべてのプラットフォーム、すべての形式で (C++ EH など) エラー条件は成立しています。

## <a name="see-also"></a>参照

[MSVC のセキュリティ機能](https://blogs.msdn.microsoft.com/vcblog/2017/06/28/security-features-in-microsoft-visual-c/)
