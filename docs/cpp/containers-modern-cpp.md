---
title: コンテナー (Modern C) |Microsoft Docs
ms.custom: ''
ms.date: 1/18/2018
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2eb9419562382d3494e64dd7fb0472882fe73c13
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939040"
---
# <a name="containers-modern-c"></a>コンテナー (Modern C++)

既定では、次のように使用します。[ベクター](../standard-library/vector-class.md) C++ では優先の順次コンテナーとして。 これに相当`List<T>`.NET 言語で。

```cpp
vector<string> apples;
apples.push_back("Granny Smith");
```

使用[マップ](../standard-library/map-class.md)(いない`unordered_map`) 既定の連想コンテナーとして。 使用[設定](../standard-library/set-class.md)、 [multimap](../standard-library/multimap-class.md)、および[multiset](../standard-library/multiset-class.md)低次元の場合。

```cpp
map<string, string> apple_color;
// ...
apple_color["Granny Smith"] = "Green";
```

パフォーマンスの最適化が必要な場合は、次の使用を検討します。

- [配列](../standard-library/array-class-stl.md)の埋め込みは、クラス メンバーとしてなど、重要なときに入力します。

- 順序なし連想コンテナーはなど[unordered_map](../standard-library/unordered-map-class.md)します。 これら下の要素ごとのオーバーヘッドおよび定数時間の参照が正しく効率的に使用するは困難です。

- 並べ替えられた`vector`します。 詳細については、「[アルゴリズム](../cpp/algorithms-modern-cpp.md)」をご覧ください。

C スタイルの配列を使用しないでください。 従来の api データにアクセスする必要がありますアクセサー メソッドをなど使用`f(vec.data(), vec.size());`代わりにします。

コンテナーの詳細については、次を参照してください。 [C++ 標準ライブラリ コンテナー](../standard-library/stl-containers.md)します。

## <a name="see-also"></a>関連項目

[C++ へようこそ](../cpp/welcome-back-to-cpp-modern-cpp.md)  
[C++ 言語リファレンス](../cpp/cpp-language-reference.md)  
[.NET 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)  
