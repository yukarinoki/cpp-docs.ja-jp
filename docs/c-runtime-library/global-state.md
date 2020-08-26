---
title: CRT でのグローバル状態
ms.date: 04/02/2020
helpviewer_keywords:
- CRT global state
ms.openlocfilehash: a794f201184c10c11611138d30d14b36b00405a7
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845186"
---
# <a name="global-state-in-the-crt"></a>CRT でのグローバル状態

ユニバーサル C ランタイム (UCRT) の一部の関数は、グローバル状態を使用します。 たとえば、は `setlocale()` プログラム全体のロケールを設定します。これは、桁区切り記号、テキストコードページなどに影響します。

UCRT のグローバル状態は、アプリケーションと OS 間で共有されません。 たとえば、アプリケーションがを呼び出す場合、 `setlocale()` C ランタイムを使用する OS コンポーネントのロケールには影響しません。その逆も同様です。

## <a name="os-specific-versions-of-crt-functions"></a>CRT 関数の OS 固有バージョン

UCRT では、グローバル状態と対話する関数に "ツイン" 関数があります。この関数の先頭にはが付き `_o_` ます。 次に例を示します。

- `setlocale()` アプリ固有のグローバルな状態に影響します。
- `_o_setlocale()` アプリではなく、すべての OS コンポーネントによって共有されるグローバル状態に影響を及ぼします。

これらの "ツイン" 関数の唯一の違いは、グローバル CRT 状態の読み取り/書き込みを行うときに OS 固有のバージョン (つまり、で始まるバージョン) では、 `_o_` アプリのグローバル状態のコピーではなく、グローバル状態の os コピーを使用することです。

これらの関数の OS 固有のバージョンは、に `ucrt.osmode.lib` あります。 たとえば、の OS 固有バージョンは次のようになります。 `setlocale()``_o_setlocale()`

コンポーネントの CRT 状態をアプリの CRT 状態から分離するには、次の2つの方法があります。

- コンパイラオプション/MT (release) または MTd (デバッグ) を使用して、コンポーネントを静的にリンクします。 詳細については、「 [/md、/mt、/ld](../build/reference/md-mt-ld-use-run-time-library.md)」を参照してください。 静的リンクによってバイナリサイズが大幅に増加することに注意してください。
- Windows 10 20H2 以降では、crt に動的にリンクすることで CRT 状態の分離を取得しますが、OS モードのエクスポート ( _o_で始まる関数) を呼び出します。 OS モードのエクスポートを呼び出すには、前と同じように静的にリンクしますが、リンカーオプション (release) または (debug) を使用して静的な UCRT を無視し `/NODEFAULTLIB:libucrt.lib` `/NODEFAULTLIB:libucrtd.lib` ます。詳細については、「 [/NODEFAULTLIB (ライブラリを無視する)](../build/reference/nodefaultlib-ignore-libraries.md) 」を参照してください。 とを `ucrt.osmode.lib` リンカー入力に追加します。

> [!Note]
> ソースコードでは、では `setlocale()` なく、を記述し `_o_setlocale()` ます。 に対してリンクすると `ucrt.osmode.lib` 、リンカーは自動的に OS 固有の関数のバージョンに置き換えます。 つまり、は `setlocale()` に置き換えられ `_o_setlocale()` ます。

に対するリンク `ucrt.osmode.lib` は、アプリモードでのみ使用できる UCRT 呼び出しを無効にします。 これらを呼び出そうとすると、リンクエラーが発生します。

## <a name="global-state-affected-by-appos-separation"></a>アプリと OS の分離の影響を受けるグローバルな状態

アプリと OS の状態の分離によって影響を受けるグローバルな状態には、次のものが含まれます。

- [ロケールデータ](locale.md)
- [シグナルによっ](reference/signal.md)て設定されるシグナルハンドラー
- [終了](reference/set-terminate-crt.md)によって設定される終了ルーチン
- [errno と _doserrno](errno-doserrno-sys-errlist-and-sys-nerr.md)
- [Rand](reference/rand.md)および[srand](reference/srand.md)で使用されるランダムな数値生成状態
- ユーザーが解放する必要のないバッファーを返す関数:   [strtok、wcstok、_mbstok](reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) [Tmpnam、_wtmpnam](reference/tempnam-wtempnam-tmpnam-wtmpnam.md) [asctime、_wasctime](reference/asctime-wasctime.md) [gmtime、_gmtime32、_gmtime64](reference/gmtime-gmtime32-gmtime64.md) [_fcvt](reference/fcvt.md) [_ecvt](reference/ecvt.md) [strerror、_strerror、_wcserror、__wcserror](reference/strerror-strerror-wcserror-wcserror.md)
- _Putch によって使用されるバッファー、 [_putwch](reference/putch-putwch.md)
- [_set_invalid_parameter_handler、_set_thread_local_invalid_parameter_handler](reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)
- [_set_new_handler](reference/set-new-handler.md) と [_set_new_mode](reference/set-new-mode.md)
- [fmode](text-and-binary-mode-file-i-o.md)
- [タイムゾーン情報](time-management.md)

## <a name="see-also"></a>関連項目

[C ランタイムライブラリリファレンス](c-run-time-library-reference.md)
