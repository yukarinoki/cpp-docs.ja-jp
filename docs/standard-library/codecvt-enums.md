---
description: '詳細については、次を参照してください: &lt; codecvt &gt; 列挙型'
title: '&lt;codecvt&gt; 列挙型'
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::codecvt_mode
ms.assetid: 46a8b073-01bc-46d3-b3d3-a8540f9422c1
helpviewer_keywords:
- std::codecvt_mode
ms.openlocfilehash: bcd40f72f563b3ecf91125f7167f206d4b1b6517
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234060"
---
# <a name="ltcodecvtgt-enums"></a>&lt;codecvt&gt; 列挙型

## <a name="codecvt_mode-enumeration"></a><a name="codecvt_mode"></a> codecvt_mode 列挙型

[ロケール](../standard-library/locale-class.md)ファセットの構成情報を指定します。

```cpp
enum codecvt_mode {
    consume_header = 4,
    generate_header = 2,
    little_endian = 1
};
```

### <a name="remarks"></a>解説

列挙体は、で宣言されたロケールファセットに構成情報を提供する3つの定数を定義し [\<codecvt>](../standard-library/codecvt.md) ます。 それぞれの値は次のとおりです。

- `consume_header`。マルチバイト シーケンスの読み取り時に初期ヘッダー シーケンスを使用し、読み取られる後続のマルチバイト シーケンスのエンディアンを決定します。

- `generate_header`。マルチバイト シーケンスの書き込み時に初期ヘッダー シーケンスを生成し、書き込まれる後続のマルチバイト シーケンスのエンディアンを提供します。

- `little_endian`。既定のビッグ エンディアン順ではなく、リトル エンディアン順でマルチバイト シーケンスを生成します。

これらの定数は任意の組み合わせで論理和を指定することができます。

## <a name="see-also"></a>関連項目

[\<codecvt>](../standard-library/codecvt.md)
