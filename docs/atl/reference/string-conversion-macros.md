---
title: 文字列変換マクロ
ms.date: 11/04/2016
f1_keywords:
- atlconv/ATL::DEVMODEA2W
- atlconv/ATL::TEXTMETRICA2W
- atlconv/ATL::DEVMODEOLE2T
- atlconv/ATL::TEXTMETRICOLE2T
- atlconv/ATL::DEVMODET2OLE
- atlconv/ATL::TEXTMETRICT2OLE
- atlconv/ATL::DEVMODEW2A
- atlconv/ATL::TEXTMETRICW2A
ms.assetid: 2ff7c0b6-2bde-45fe-897f-6128e18e0c27
ms.openlocfilehash: 8df496b78334d26e7d3664642b2e9d93d6149843
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325853"
---
# <a name="string-conversion-macros"></a>文字列変換マクロ

これらのマクロは、文字列変換機能を提供します。

## <a name="atl-and-mfc-string-conversion-macros"></a><a name="atl_and_mfc_string_conversion_macros"></a>ATL および MFC 文字列変換マクロ

ここで説明する文字列変換マクロは、ATL と MFC の両方に対して有効です。 MFC 文字列変換の詳細については、「 [TN059: MFC MBCS/Unicode 変換マクロ](../../mfc/tn059-using-mfc-mbcs-unicode-conversion-macros.md)と[MFC マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)を使用する 」を参照してください。

## <a name="devmode-and-textmetric-string-conversion-macros"></a><a name="devmode_and_textmetric_string_conversion_macros"></a>DEVMODE とテキスト形式の文字列変換マクロ

これらのマクロは[、DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea)または[TEXTMETRIC](/windows/win32/api/wingdi/ns-wingdi-textmetricw)構造体のコピーを作成し、新しい構造体内の文字列を新しい文字列型に変換します。 マクロは、新しい構造体のスタックにメモリを割り当て、新しい構造体へのポインターを返します。

```cpp
MACRONAME( address_of_structure )
```

### <a name="remarks"></a>解説

次に例を示します。

[!code-cpp[NVC_ATL_Utilities#128](../../atl/codesnippet/cpp/string-conversion-macros_1.cpp)]

および

[!code-cpp[NVC_ATL_Utilities#129](../../atl/codesnippet/cpp/string-conversion-macros_2.cpp)]

マクロ名では、ソース構造の文字列型が左側 (**たとえば、A**) で、変換先の構造体の文字列型が右側にあります (**たとえば、W)。** LPSTR**の略****、OLE**は LPOLESTR、T は LPTSTR、W は LPWSTR の略です。 **T** **W**

したがって、DEVMODEA2W は`DEVMODE`LPSTR 文字列を持`DEVMODE`つ構造体を LPWSTR 文字列を持つ構造体に`TEXTMETRIC`コピーし、LPOLESTR 文字列`TEXTMETRIC`を持つ構造体を LPTSTR 文字列を持つ構造体にコピーします。

構造体で変換される`DEVMODE`2 つの文字列は、デバイス`dmDeviceName`名 ( )`dmFormName`とフォーム名 ( ) です。 `DEVMODE`文字列変換マクロは、構造サイズ (`dmSize`) も更新します。

`TEXTMETRIC`構造体で変換される 4 つの文字列は、最初`tmFirstChar`の文字 (`tmLastChar`) 、最後の`tmDefaultChar`文字 ( )`tmBreakChar`、デフォルトの文字 ( ) 、およびブレーク文字 ( ) です。

および`TEXTMETRIC`文字列変換マクロ`DEVMODE`の動作は、有効なコンパイラ ディレクティブ (存在する場合) によって異なります。 ソースの型とターゲットの型が同じである場合、変換は実行されません。 コンパイラ ディレクティブは、次のように**T**と**OLE**を変更します。

|有効なコンパイラ ディレクティブ|T の変更後|OLE の変更後|
|----------------------------------|---------------|-----------------|
|none|**A**|**W**|
|**\_Unicode**|**W**|**W**|
|**OLE2ANSI**|**A**|**A**|
|ユニコードと**OLE2ANSI** ** \_**|**W**|**A**|

次の表は、`DEVMODE`および`TEXTMETRIC`文字列変換マクロを示しています。

|||
|-|-|
|デモデヤ2W|2W|
|デモデオレ2T|テキストメトリック2T|
|デモデト2オール|テキストメトリック2OLE|
|デモデウ2A|テキストメトリック2A|

## <a name="see-also"></a>関連項目

[マクロ](../../atl/reference/atl-macros.md)
