---
description: '詳細情報: &lt; codecvt&gt;'
title: '&lt;codecvt&gt;'
ms.date: 11/04/2016
f1_keywords:
- <codecvt>
helpviewer_keywords:
- codecvt header
ms.assetid: d44ee229-00d5-4761-9b48-0c702122789d
ms.openlocfilehash: 739389fa432a2eef86533951385078e13bc05684
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "98126633"
---
# <a name="ltcodecvtgt"></a>&lt;codecvt&gt;

クラステンプレート [codecvt](../standard-library/codecvt-class.md)に基づいてオブジェクトを記述するいくつかのクラステンプレートを定義します。 これらのオブジェクトは、型の値のシーケンスと型の値のシーケンスとの間の変換を制御する [ロケールファセット](../standard-library/locale-class.md#facet_class) として使用でき `Elem` **`char`** ます。

## <a name="syntax"></a>構文

```cpp
#include <codecvt>
```

## <a name="remarks"></a>解説

このヘッダーで宣言されているロケール ファセットは、いくつかの文字エンコード間の変換を行います。 ワイド文字 (固定サイズの整数で表され、プログラム内に格納される) については、次のようになります。

- UCS-4 は、32 ビットの整数で表される、プログラムにおける Unicode (ISO 10646) のエンコード形式です。

- UCS-2 は、16 ビットの整数で表される、プログラムにおける Unicode のエンコード形式です。

- UTF-16 は、1 つまたは 2 つの 16 ビットの整数で表される、プログラムにおける Unicode のエンコード形式です  (これは、標準 C または標準 C++ の有効なワイド文字エンコードの要件をすべて満たしているわけではないことに注意してください。 しかし、これ自体は広く利用されています)。

バイトストリーム (ファイルに格納されている、バイトシーケンスとして送信される、またはの配列内のプログラム内に格納されている) の場合は、 **`char`** 次のようになります。

- UTF-8 は、バイト順が確定されている 1 つ以上の 8 ビット バイトで表される、バイト ストリームにおける Unicode のエンコード形式です。

- UTF-16LE は、16 ビット整数がそれぞれ 2 つの 8 ビット バイト (最初が下位バイト) で表される UTF-16 と同様のバイト ストリームにおける Unicode のエンコード形式です。

- UTF-16BE は、16 ビット整数がそれぞれ 2 つの 8 ビット バイト (最初が上位バイト) で表される、UTF-16 と同様のバイト ストリームにおける Unicode のエンコード形式です。

### <a name="enumerations"></a>列挙型

|名前|説明|
|-|-|
|[codecvt_mode](../standard-library/codecvt-enums.md#codecvt_mode)|ロケール ファセットの構成情報を指定します。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[codecvt_utf8](codecvt-utf8-class.md)|UCS-2 または UCS-4 としてエンコードされたワイド文字と、UTF-8 としてエンコードされたバイト ストリームを変換するロケール ファセットを表します。|
|[codecvt_utf8_utf16](codecvt-utf8-utf16-class.md)|UTF-16 としてエンコードされたワイド文字と、UTF-8 としてエンコードされたバイト ストリームを変換するロケール ファセットを表します。|
|[codecvt_utf16](codecvt-utf16-class.md)|UCS-2 または UCS-4 としてエンコードされたワイド文字と、UTF-16LE または UTF-16BE としてエンコードされたバイト ストリームを変換するロケール ファセットを表します。|

## <a name="requirements"></a>必要条件

**ヘッダー:**\<codecvt>

**名前空間:** std

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)
