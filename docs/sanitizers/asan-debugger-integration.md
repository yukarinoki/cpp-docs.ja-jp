---
title: Visual Studio AddressSanitizer 拡張機能ライブラリ (VCASan)
description: Vcasan .lib の技術説明。
ms.date: 03/02/2021
f1_keywords:
- vcasan
helpviewer_keywords:
- vcasan.lib
- vcasan
- vcasand.lib
- libvcasan.lib
- libvcasand.lib
ms.openlocfilehash: 8728fead94b5d2b4827b34f1a5461c08c821f2e7
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102471036"
---
# <a name="visual-studio-addresssanitizer-extended-functionality-library-vcasan"></a>Visual Studio AddressSanitizer 拡張機能ライブラリ (VCAsan)

ライブラリには、 *`VCAsan*.lib`* Visual Studio の拡張デバッガー IDE 機能が実装されています。 これらの機能を使用すると、IDE でライブデバッグセッションでの AddressSanitizer エラーを表示したり、メタデータを含むクラッシュダンプファイルを保存することによってオフラインにすることができます。 ライブラリは、AddressSanitizer が MSVC コンパイラによって有効になっている場合はいつでもリンクされます。

## <a name="vcasan-library-inventory"></a>ライブラリインベントリを VCAsan

| Runtime オプション | VCAsan リンクライブラリ  |
|---------------|----------------------|
| **`/MT`**           | *`libvcasan.lib`*        |
| **`/MD`**           | *`vcasan.lib`*           |
| **`/MTd`**          | *`libvcasand.lib`*       |
| **`/MDd`**          | *`vcasand.lib`*          |

## <a name="vcasan-library-features"></a>VCAsan library の機能

### <a name="rich-addresssanitizer-error-report-window-in-visual-studio-ide"></a>Visual Studio IDE のリッチ AddressSanitizer エラーレポートウィンドウ

VCAsan ライブラリは、インターフェイス関数を使用して、AddressSanitizer ランタイム内のコールバックを登録し [`__asan_set_error_report_callback`](https://github.com/llvm/llvm-project/blob/1ba5ea67a30170053964a28f2f47aea4bb7f5ff1/compiler-rt/include/sanitizer/asan_interface.h#L256) ます。 AddressSanitizer レポートが生成された場合、このコールバックを使用して、Visual Studio でキャッチされた例外をスローします。 Visual Studio は、例外データを使用して、IDE でユーザーに表示されるメッセージを生成します。

> [!NOTE]
> VCAsan ライブラリは、AddressSanitizer ランタイムにコールバック関数を登録します。 コードがこの登録関数をもう一度呼び出すと、VCAsan ライブラリコールバックの登録が上書きされます。 その結果、すべての Visual Studio IDE 統合が失われます。 既定の IDE ユーザーエクスペリエンスに戻ります。 また、コールバックが失われるようにユーザーの呼び出しが登録されている可能性もあります。 いずれかの問題が発生した場合は、 [バグを報告](https://aka.ms/feedback/report?space=62)します。

### <a name="save-addresssanitizer-errors-in-a-new-type-of-crash-dump-file"></a>新しい種類のクラッシュダンプファイルに AddressSanitizer エラーを保存する

VCAsan ライブラリを実行可能ファイルにリンクすると、ユーザーは実行時にクラッシュダンプを生成できるようになります。 その後、診断されたエラーが発生したときに、AddressSanitizer ランタイムによってダンプファイルが生成されます。 この機能を有効にするために、ユーザーは次のようなコマンドを使用して環境変数を設定し `ASAN_SAVE_DUMPS` ます。

`set ASAN_SAVE_DUMPS=MyFileName.dmp`

Visual Studio IDE の規則に従うには、ファイルのサフィックスが .dmp である必要があります。

ダンプファイルがに対して指定されている場合は、次のようになり `ASAN_SAVE_DUMPS` ます。 AddressSanitizer ランタイムによってエラーがキャッチされると、エラーに関連付けられたメタデータを含むクラッシュダンプファイルが保存されます。 Visual Studio バージョン16.9 以降のデバッガーでは、ダンプファイルに保存されているメタデータを解析できます。 テストごとにを設定して `ASAN_SAVE_DUMPS` 、これらのバイナリ成果物を格納し、適切なソースインデックスを使用して IDE でそれらを表示できます。

## <a name="see-also"></a>関連項目

[AddressSanitizer の概要](./asan.md)\
[AddressSanitizer の既知の問題](./asan-known-issues.md)\
[AddressSanitizer ビルドと言語リファレンス](./asan-building.md)\
[AddressSanitizer ランタイムリファレンス](./asan-runtime.md)\
[AddressSanitizer shadow bytes](./asan-shadow-bytes.md)\
[AddressSanitizer クラウドまたは分散テスト](./asan-offline-crash-dumps.md)\
[AddressSanitizer エラーの例](./asan-error-examples.md)
