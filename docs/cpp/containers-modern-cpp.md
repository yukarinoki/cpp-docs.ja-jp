---
title: コンテナー (Modern C) |Microsoft ドキュメント
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
ms.openlocfilehash: 49a77234b679fd61d801bb78d751891467d6b4e0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32412076"
---
# <a name="containers-modern-c"></a>コンテナー (Modern C++)

既定では、次のように使用します。[ベクター](../standard-library/vector-class.md) C++ では優先されるシーケンシャルなコンテナーとして。 これに相当`List<T>`.NET 言語でします。

```cpp
vector<string> apples;
apples.push_back("Granny Smith");
```

使用して[マップ](../standard-library/map-class.md)(いない`unordered_map`) 既定の連想コンテナーとして。 使用して[設定](../standard-library/set-class.md)、 [multimap](../standard-library/multimap-class.md)、および[multiset](../standard-library/multiset-class.md)マルチ (&)、逆の場合。

```cpp
map<string, string> apple_color;
// ...
apple_color["Granny Smith"] = "Green";
```

パフォーマンスの最適化が必要な場合は、次の使用を検討します。

- [配列](../standard-library/array-class-stl.md)埋め込みは、クラス メンバーとしてなど、重要なときに入力します。

- 順序なし連想コンテナーはなど[unordered_map](../standard-library/unordered-map-class.md)です。 これら下の要素ごとのオーバーヘッドありが一定時間の参照が可能正しく効率的に使用するは困難です。

- 並べ替えられた**ベクター**です。 詳細については、「[アルゴリズム](../cpp/algorithms-modern-cpp.md)」をご覧ください。

C スタイルの配列を使用しないでください。 データへのアクセスを指示する必要がある従来の api には、アクセサー メソッドをなど使用`f(vec.data(), vec.size());`代わりにします。

コンテナーの詳細については、次を参照してください。 [C++ 標準ライブラリのコンテナー](../standard-library/stl-containers.md)です。

## <a name="see-also"></a>関連項目

[C++ へようこそ](../cpp/welcome-back-to-cpp-modern-cpp.md)  
[C++ 言語リファレンス](../cpp/cpp-language-reference.md)  
[.NET 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)  
