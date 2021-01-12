---
description: '詳細情報: &lt; 値&gt;'
title: '&lt;値> (C++ ドキュメントコメント)'
ms.date: 11/04/2016
f1_keywords:
- <value>
helpviewer_keywords:
- value C++ XML tag
- <value> C++ XML tag
ms.assetid: 0ba0a0d5-bcd7-4862-a169-83f2721ad80e
ms.openlocfilehash: 5ebab554a33ff0d90b9306f3aec56b2552e18c5a
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "98126326"
---
# <a name="ltvaluegt"></a>&lt;value&gt;

\<value>タグを使用すると、プロパティとプロパティのアクセサーメソッドを記述できます。 Visual Studio 統合開発環境でコードウィザードを使用してプロパティを追加すると、新しいプロパティのタグが追加されることに注意 [\<summary>](summary-visual-cpp.md) してください。 その後、手動で \<value> タグを追加してプロパティが表す値を記述する必要があります。

## <a name="syntax"></a>構文

```
<value>property-description</value>
```

#### <a name="parameters"></a>パラメーター

*property-description*<br/>
プロパティの説明。

## <a name="remarks"></a>Remarks

ドキュメントコメントをファイルに処理するために、 [/doc](doc-process-documentation-comments-c-cpp.md) を使用してコンパイルします。

## <a name="example"></a>例

```cpp
// xml_value_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_value_tag.dll
using namespace System;
/// Text for class Employee.
public ref class Employee {
private:
   String ^ name;
   /// <value>Name accesses the value of the name data member</value>
public:
   property String ^ Name {
      String ^ get() {
         return name;
      }
      void set(String ^ i) {
         name = i;
      }
   }
};
```

## <a name="see-also"></a>関連項目

[XML に関するドキュメント](xml-documentation-visual-cpp.md)
