---
title: '&lt;> の一覧表示 (C++ ドキュメントコメント)'
ms.date: 11/04/2016
f1_keywords:
- list
helpviewer_keywords:
- list C++ XML tag
- <list> C++ XML tag
ms.assetid: c792a10b-0451-422c-9aa0-604116e69d64
ms.openlocfilehash: 24f9b17c67b8f951743fd51c04266b05dad235c7
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041966"
---
# <a name="ltlistgt-and-ltlistheadergt"></a>&lt;list &gt; と &lt; listheader&gt;

\<listheader> ブロックを使用して、テーブルまたは定義リストの見出し行を定義します。 テーブルを定義するときにのみ、見出しの用語のエントリを指定する必要があります。

## <a name="syntax"></a>構文

```xml
<list type="bullet" | "number" | "table">
   <listheader>
      <term>term</term>
      <description>description</description>
   </listheader>
   <item>
      <term>term</term>
      <description>description</description>
   </item>
</list>
```

#### <a name="parameters"></a>パラメーター

*句*<br/>
定義される用語であり、`description` で定義されます。

*description*<br/>
行頭文字または番号付きリストの項目、または `term` の定義です。

## <a name="remarks"></a>Remarks

リストの各項目は、\<item> ブロックで指定されます。 定義リストを作成する場合は、`term` と `description` の両方を指定する必要があります。 ただし、テーブル、箇条書きリスト、または番号付きリストの場合は、`description` のエントリを指定するだけで済みます。

リストまたはテーブルでは、必要な数の \<item> ブロックを使用できます。

ドキュメントコメントをファイルに処理するために、 [/doc](doc-process-documentation-comments-c-cpp.md) を使用してコンパイルします。

## <a name="example"></a>例

```cpp
// xml_list_tag.cpp
// compile with: /doc /LD
// post-build command: xdcmake xml_list_tag.dll
/// <remarks>Here is an example of a bulleted list:
/// <list type="bullet">
/// <item>
/// <description>Item 1.</description>
/// </item>
/// <item>
/// <description>Item 2.</description>
/// </item>
/// </list>
/// </remarks>
class MyClass {};
```

## <a name="see-also"></a>関連項目

[XML に関するドキュメント](xml-documentation-visual-cpp.md)
