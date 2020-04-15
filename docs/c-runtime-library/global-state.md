---
title: CRT のグローバル状態
ms.date: 04/02/2020
helpviewer_keywords:
- CRT global state
ms.openlocfilehash: 487418da104b2edbc45b5d3a664e4385394ada31
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377600"
---
# <a name="global-state-in-the-crt"></a>CRT のグローバル状態

ユニバーサル C ランタイム (UCRT) の一部の関数は、グローバル状態を使用します。 たとえば、`setlocale()`プログラム全体のロケールを設定し、桁区切り記号やテキスト コード ページなどに影響します。

UCRT のグローバル状態は、アプリケーションと OS 間で共有されません。 たとえば、アプリケーションが を呼`setlocale()`び出す場合、C ランタイムを使用する OS コンポーネントのロケールには影響しません。

## <a name="os-specific-versions-of-crt-functions"></a>CRT 関数の OS 固有バージョン

UCRT では、グローバル状態と対話する関数には、プレフィックスが付いた "ツイン"`_o_`関数があります。 次に例を示します。

    `setlocale()` affects global state specific to the app.
    `_o_setlocale()` affects global state shared by all OS components, but not apps.

これらの "ツイン" 関数の唯一の違いは、グローバル CRT 状態を読み書きするときに、OS 固有のバージョン (つまり`_o_`、で始まるバージョン) が、アプリのグローバル状態のコピーではなく、グローバル状態の OS コピーを使用することです。

これらの機能の OS 固有のバージョンは`ucrt.osmode.lib`に記載されています。 たとえば、OS 固有のバージョンは`setlocale()``_o_setlocale()`

コンポーネントの CRT 状態をアプリの CRT 状態から分離するには、次の 2 つの方法があります。

- コンパイラ オプション /MT (リリース) または MTd (デバッグ) を使用して、コンポーネントを静的にリンクします。 詳細については[、「/MD、/MT、/LD」](https://docs.microsoft.com/cpp/build/reference/md-mt-ld-use-run-time-library?view=vs-2019)を参照してください。 静的リンクはバイナリ サイズを大幅に増加させることに注意してください。
- Windows 10 20H2 以降では、CRT に動的にリンクすることで CRT 状態の分離を取得しますが、OS モードのエクスポート _(o_で始まる関数) を呼び出します。 OS モード・エクスポートを呼び出す場合は、前と同じ静的リンクを使用しますが、リン`/NODEFAULTLIB:libucrt.lib`カー・オプション`/NODEFAULTLIB:libucrtd.lib`(リリース) または (デバッグ) 詳細については[、/NODEFAULTLIB (ライブラリーの無視) を](https://docs.microsoft.com/cpp/build/reference/nodefaultlib-ignore-libraries?view=vs-2019)使用して静的 UCRT を無視してください。 そして、`ucrt.osmode.lib`リンカー入力に追加します。

> [!Note]
> ソース コードで、`setlocale()`ではなく`_o_setlocale()`を記述します。 にリンク`ucrt.osmode.lib`すると、リンカーは OS 固有のバージョンの関数を自動的に置き換えます。 つまり、`setlocale()`で`_o_setlocale()`置き換えられます。

これに対`ucrt.osmode.lib`するリンクは、アプリ モードでのみ使用可能な一部の UCRT 呼び出しを無効にします。 これらを呼び出そうとすると、リンク エラーが発生します。

## <a name="global-state-affected-by-appos-separation"></a>アプリ/OS 分離の影響を受けるグローバル状態

アプリと OS の状態の分離によって影響を受けるグローバル状態には、次のものが含まれます。

- [ロケールデータ](locale.md)
- シグナルによって設定された[シグナル](reference/signal.md)ハンドラ
- 終了によって設定された[終了](reference/set-terminate-crt.md)ルーチン
- [エラーノと_doserrno](errno-doserrno-sys-errlist-and-sys-nerr.md)
- [ランド](reference/rand.md)と[スランド](reference/srand.md)で使用される乱数生成状態
- ユーザーが解放する必要のないバッファを返す関数: [strtok, wcstok, _mbstok](reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) [Tmpnam, _wtmpnam](reference/tempnam-wtempnam-tmpnam-wtmpnam.md) [asctime, _wasctime](reference/asctime-wasctime.md) [gmtime, _gmtime32,](reference/gmtime-gmtime32-gmtime64.md) [_fcvt](reference/fcvt.md) _gmtime64 [_ecvt_ecvtstrerror、_strerror、_wcserror、__wcserror](reference/strerror-strerror-wcserror-wcserror.md) [_ecvt](reference/ecvt.md)
- _putchが使用するバッファ[_putwch](reference/putch-putwch.md)
- [_set_invalid_parameter_handler、_set_thread_local_invalid_parameter_handler](reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)
- [_set_new_handler](reference/set-new-handler.md)と[_set_new_mode](reference/set-new-mode.md)
- [fmode](text-and-binary-mode-file-i-o.md)
- [タイム ゾーン情報](time-management.md)

## <a name="see-also"></a>関連項目

[C ランタイム ライブラリ リファレンス](c-run-time-library-reference.md)