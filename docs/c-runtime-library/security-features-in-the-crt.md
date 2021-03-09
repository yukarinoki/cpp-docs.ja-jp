---
title: CRT のセキュリティ機能
description: Microsoft C ランタイムのセキュリティで保護された CRT 関数の概要を説明します。
ms.date: 09/29/2020
ms.topic: conceptual
f1_keywords:
- _CRT_SECURE_NO_DEPRECATE
- _CRT_NONSTDC_NO_WARNINGS
- _CRT_SECURE_NO_WARNINGS
helpviewer_keywords:
- security deprecation warnings [C++]
- CRT_NONSTDC_NO_DEPRECATE
- buffers [C++], buffer overruns
- deprecation warnings (security-related), disabling
- _CRT_NONSTDC_NO_WARNINGS
- security [CRT]
- _CRT_SECURE_NO_WARNINGS
- _CRT_NONSTDC_NO_DEPRECATE
- _CRT_SECURE_NO_DEPRECATE
- security-enhanced CRT
- CRT_SECURE_NO_WARNINGS
- CRT_SECURE_NO_DEPRECATE
- deprecation warnings (security-related)
- buffer overruns
- CRT_NONSTDC_NO_WARNINGS
- CRT, security enhancements
- parameters [C++], validation
ms.assetid: d9568b08-9514-49cd-b3dc-2454ded195a3
ms.openlocfilehash: 96642e5e79f9df7c0a063582408c0463600be20f
ms.sourcegitcommit: 90c300b74f6556cb5d989802d2e80d79542f55e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "102514682"
---
# <a name="security-features-in-the-crt"></a>CRT のセキュリティ機能

多くの古い CRT 関数には、セキュリティが強化された新しいバージョンがあります。 セキュリティで保護された関数が存在する場合、低いセキュリティ レベルの古いバージョンは非推奨としてマークされ、新しいバージョンには `_s` ("secure") のサフィックスが付いています。

このコンテキストでは、"非推奨" とは、関数の使用が推奨されないことを意味します。 関数が CRT から削除されるようにスケジュールされているわけではありません。

セキュリティで保護された関数は、セキュリティエラーを回避または修正しません。 代わりに、発生したエラーをキャッチします。 エラー条件に対して追加のチェックを行います。 エラーが発生した場合は、エラーハンドラーを呼び出します (「 [パラメーターの検証](../c-runtime-library/parameter-validation.md)」を参照してください)。

たとえば、関数は、 `strcpy` コピーする文字列がコピー先のバッファーに対して大きすぎるかどうかを判断できません。 セキュリティで保護された対応するは、 `strcpy_s` バッファーのサイズをパラメーターとして受け取ります。 バッファーオーバーランが発生するかどうかを判断できます。 を使用し `strcpy_s` て11文字を10文字のバッファーにコピーする場合は、その部分でエラーが発生します。では、間違っていることを修正することは `strcpy_s` できません。 しかし、エラーを検出して、無効なパラメーターハンドラーを呼び出すことによって通知することができます。

## <a name="eliminating-deprecation-warnings"></a>非推奨に関する警告を除去する

低いセキュリティ レベルの古い関数に対する非推奨警告を除去するには、いくつかの方法があります。 `_CRT_SECURE_NO_WARNINGS` を定義するか、[warning](../preprocessor/warning.md) プラグマを使用するのが、最も簡単な方法です。 では、非推奨の警告は無効になりますが、警告の原因となったセキュリティの問題は引き続き存在します。 廃止時の警告を有効にしたままにして、新しい CRT のセキュリティ機能を利用することをお勧めします。

C++ では、これを行う最も簡単な方法は、 [セキュリティで保護さ](../c-runtime-library/secure-template-overloads.md)れたテンプレートのオーバーロードを使用することです。 これにより、多くの場合、非推奨の関数の呼び出しをセキュリティで保護されたバージョンの関数の呼び出しに置き換えることにより、非推奨の警告が除去されます。 たとえば、この非推奨とされている `strcpy` の呼び出しについて考えます：

```
char szBuf[10];
strcpy(szBuf, "test"); // warning: deprecated
```

`_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` を 1 として定義すると、`strcpy` の呼び出しが、バッファー オーバーランを防ぐ `strcpy_s` の呼び出しに変更され、警告は除去されます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../c-runtime-library/secure-template-overloads.md)」を参照してください。

セキュリティで保護されたテンプレート オーバーロードのない、非推奨の関数の場合、セキュリティで保護されたバージョンを使用するように手動でコードを更新することを強くお勧めします。

セキュリティには関連しませんが、非推奨に関する警告が発生する別の要因として、POSIX 関数があります。 POSIX の関数名を標準に沿った名前に置き換えるか ([access](../c-runtime-library/reference/access-crt.md) を [_access](../c-runtime-library/reference/access-waccess.md) にするなど)、`_CRT_NONSTDC_NO_WARNINGS` を定義して、POSIX 関連の非推奨に関する警告を無効にします。 詳細については、「 [互換性](compatibility.md)」を参照してください。

## <a name="additional-security-features"></a>その他のセキュリティ機能

セキュリティ機能には次のようなものがあります。

- `Parameter Validation`. セキュリティで保護された関数、およびそれらに対応していない機能の多くは、パラメーターを検証します。 検証には次のものが含まれます。

  - **NULL** 値があるかどうかを確認しています。
  - 列挙値が有効であるかどうかのチェック。
  - 整数値が有効な範囲にあるかどうかのチェック。

- 詳細については、「[パラメーターの検証](../c-runtime-library/parameter-validation.md)」を参照してください。

- 開発者も無効なパラメーターのハンドラーを利用できるようになりました。 関数が無効なパラメーターを検出すると、アプリケーションをアサートして終了するのではなく、 [_set_invalid_parameter_handler、_set_thread_local_invalid_parameter_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)を使用してこれらの問題を確認することができます。

- `Sized Buffers`. バッファーサイズは、バッファーに書き込むセキュリティで保護された任意の関数に渡す必要があります。 セキュリティで保護されたバージョンでは、バッファーが書き込み前に十分な大きさであることを確認します。 これは、悪意のあるコードの実行を許可する危険なバッファーオーバーランエラーを回避するのに役立ちます。 通常、これらの関数は `errno` エラーコードを返し、バッファーのサイズが小さすぎる場合は無効なパラメーターハンドラーを呼び出します。 `gets` など、入力バッファーからの読み込みを行う関数のセキュリティで保護されたバージョンでは、最大サイズを指定する必要があります。

- `Null termination`. 中断されていない可能性のある文字列を残した一部の関数にはセキュリティで保護されたバージョンがあるため、文字列は正しく null で終了します。

- `Enhanced error reporting`. セキュリティで保護された関数は、既存の関数で使用できなかったエラー情報を含むエラーコードを返します。 セキュリティで保護された関数と多くの既存の関数は、 `errno` `errno` より適切なエラーレポートを提供するために、多くの場合、コードの種類を設定して返します。

- `Filesystem security`. セキュリティで保護されたファイル I/O API では、既定のケースで安全なファイル アクセスをサポートします。

- `Windows security`. セキュリティで保護されたプロセス API では、セキュリティ ポリシーが適用され、ACL を指定できます。

- `Format string syntax checking`. 無効な文字列が検出されます。たとえば、`printf` 書式指定文字列の不正な型フィールド文字を使用した場合です。

## <a name="see-also"></a>こちらもご覧ください

[パラメーターの検証](../c-runtime-library/parameter-validation.md)<br/>
[セキュリティで保護されたテンプレートのオーバーロード](../c-runtime-library/secure-template-overloads.md)<br/>
[C ランタイム (CRT) と C++ 標準ライブラリ (STL) `.lib` ファイル](../c-runtime-library/crt-library-features.md)
