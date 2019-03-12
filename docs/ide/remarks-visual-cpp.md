---
title: '&lt;remarks&gt; (Visual C++)'
ms.date: 11/04/2016
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- <remarks> C++ XML tag
- remarks C++ XML tag
ms.assetid: c820083b-3192-40ab-9ec8-1472c55b4247
ms.openlocfilehash: 2a897b20cbee797bd1e9a7477e30460f2ed4064c
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "57748984"
---
# <a name="ltremarksgt-visual-c"></a>&lt;remarks&gt; (Visual C++)

\<remarks> タグを使用して、型の情報を追加し、[\<summary>](../ide/summary-visual-cpp.md) で指定された情報を補足します。 この情報は[オブジェクト ブラウザー](/visualstudio/ide/viewing-the-structure-of-code)とコード コメント Web レポートに表示されます。

## <a name="syntax"></a>構文

```
<remarks>description</remarks>
```

#### <a name="parameters"></a>パラメーター

*description*<br/>
メンバーの説明。

## <a name="remarks"></a>解説

コンパイル時に [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) を指定して、ドキュメント コメントをファイルに出力します。

## <a name="example"></a>例

```
// xml_remarks_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_remarks_tag.dll

using namespace System;

/// <summary>
/// You may have some primary information about this class.
/// </summary>
/// <remarks>
/// You may have some additional information about this class.
/// </remarks>
public ref class MyClass {};
```

## <a name="see-also"></a>関連項目

[XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)
