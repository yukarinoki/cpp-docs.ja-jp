---
title: AddressSanitizer shadow bytes
description: コンパイラによって生成されたコードと AddressSanitizer ランタイムによって書き込まれ、読み取られるシャドウバイトの技術説明。
ms.date: 03/02/2021
helpviewer_keywords:
- Shadow bytes
- AddressSanitizer shadow bytes
- Address Sanitizer shadow bytes
- ASan shadow bytes
ms.openlocfilehash: 89c3051d2e68d579f2f187fcd12b45ff52cd8a58
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102471027"
---
# <a name="addresssanitizer-shadow-bytes"></a>AddressSanitizer shadow bytes

ここでは、シャドウバイトの概念と、のランタイム実装でそれらを使用する方法について簡単に説明し [`/fsanitize=address`](../build/reference/fsanitize.md) ます。 詳細については、 [よる著書のホワイトペーパー](https://www.usenix.org/system/files/conference/atc12/atc12-final39.pdf) と [AddressSanitizer アルゴリズム](https://github.com/google/sanitizers/wiki/AddressSanitizerAlgorithm)に関する記事をご覧ください。

## <a name="core-concept"></a>主要な概念

アプリケーションの仮想アドレス空間の **8 バイト** ごとに、 **1 つのシャドウバイト** を使用して記述できます。

1つのシャドウバイトは、現在、次のようにアクセスできるバイト数を示します。

- 0は、すべて8バイトを意味します。
- 1-7 は、1 ~ 7 バイトを意味します。
- 負の数値は、ランタイムが診断のレポートに使用するためのコンテキストをエンコードします。

### <a name="shadow-byte-legend"></a>シャドウバイトの凡例

このシャドウバイトの凡例は、すべての負の数値が定義されているとします。

:::image type="content" source="./media/asan-shadow-byte-legend.png" alt-text="AddressSanitizer シャドウバイトの凡例のスクリーンショット。":::

## <a name="mapping---describing-your-address-space"></a>マッピング-アドレス空間について説明します。

アプリケーションの仮想アドレス空間 ("0-mod-8") の8バイトごとに、仮想アドレス空間内のそのスロットを示すシャドウバイトにマップできます。  このマッピングは、 **単純な shift キーと add キー** を使用して実現できます。

X86 の場合:

```cpp
char shadow_byte_value = *((Your_Address >> 3) + 0x30000000)
```

X64 の場合:

```cpp
char shadow_byte_value = *((Your_Address >> 3) + _asan_runtime_assigned_offset)
```

## <a name="code-generation---tests"></a>コード生成-テスト

コンパイラで生成されたコード、静的データ、またはランタイムのいずれかによって、特定のシャドウバイトが書き込まれる方法を検討します。 この擬似コードは、ロードまたはストアの前にチェックを生成する方法を示しています。

```cpp
ShadowAddr = (Addr >> 3) + Offset;
if (*ShadowAddr != 0) {
    ReportAndCrash(Addr);
}
```

8バイトを超えるメモリ参照をインストルメント化する場合、インストルメンテーションはやや複雑になります。 影の値が正の値 (8 バイトワードの最初の k バイトだけにアクセスできる) の場合は、アドレスの最後の3ビットを k で比較する必要があります。

```cpp
ShadowAddr = (Addr >> 3) + Offset;
k = *ShadowAddr;
if (k != 0 && ((Addr & 7) + AccessSize > k)) {
    ReportAndCrash(Addr);
}
```

ランタイムとコンパイラによって生成されたコードは、どちらもシャドウバイトの書き込みを行います。 これらのシャドウバイトは、スコープの終了またはストレージが解放されたときにアクセスを許可または取り消すことができます。 上のチェックでは、プログラムの実行時に、アプリケーションのアドレス空間にある8バイトの "スロット" を示す読み取りシャドウバイト数を確認します。 これらの明示的に生成されたチェックに加えて、ランタイムは、CRT の多くの関数をインターセプト (または "フック") した後に、シャドウバイトもチェックします。

詳細については、インターセプトした [関数](./asan-runtime.md#default-interceptors)の一覧を参照してください。

## <a name="setting-shadow-bytes"></a>シャドウバイトの設定

コンパイラによって生成されるコードと、AddressSanitizer ランタイムはシャドウバイトを書き込むことができます。 たとえば、コンパイラは、内側のスコープで定義されているスタックローカルに固定サイズのアクセスを許可するようにシャドウバイトを設定できます。 ランタイムは、データセクションのグローバル変数をシャドウバイトで囲むことができます。

## <a name="see-also"></a>関連項目

[AddressSanitizer の概要](./asan.md)\
[AddressSanitizer の既知の問題](./asan-known-issues.md)\
[AddressSanitizer ビルドと言語リファレンス](./asan-building.md)\
[AddressSanitizer ランタイムリファレンス](./asan-runtime.md)\
[AddressSanitizer クラウドまたは分散テスト](./asan-offline-crash-dumps.md)\
[AddressSanitizer デバッガーの統合](./asan-debugger-integration.md)\
[AddressSanitizer エラーの例](./asan-error-examples.md)
