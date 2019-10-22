---
title: コンテナー (Modern C++)
ms.date: 01/18/2018
ms.topic: conceptual
ms.openlocfilehash: 37b540132fc9ddc03d5eaafd33c545b5db5e7935
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926261"
---
# <a name="containers-modern-c"></a>コンテナー (Modern C++)

既定では、でC++適切なシーケンシャルコンテナーとして[ベクター](../standard-library/vector-class.md)を使用します。 これは、.net `List<T>`言語のに相当します。

```cpp
vector<string> apples;
apples.push_back("Granny Smith");
```

既定の連想コンテナー として [map](../standard-library/map-class.md) (not `unordered_map`) を使用します。 低次元 & 複数のケースには、 [set](../standard-library/set-class.md)、 [multimap](../standard-library/multimap-class.md)、およびマルチ[セット](../standard-library/multiset-class.md)を使用します。

```cpp
map<string, string> apple_color;
// ...
apple_color["Granny Smith"] = "Green";
```

パフォーマンスの最適化が必要な場合は、次の使用を検討します。

- たとえば、クラスメンバーとして埋め込む場合の[配列](../standard-library/array-class-stl.md)型。

- [Unordered_map](../standard-library/unordered-map-class.md)などの順序付けられていない連想コンテナー。 これらの要素には、要素ごとのオーバーヘッドが少なく、一定時間の参照がありますが、正確で効率的に使用するのは困難な場合があります。

- 並べ替え`vector`済み。 詳細については、「[アルゴリズム](../cpp/algorithms-modern-cpp.md)」をご覧ください。

C スタイルの配列は使用しないでください。 データへの直接アクセスを必要とする古い api の場合は、 `f(vec.data(), vec.size());`代わりになどのアクセサーメソッドを使用します。

コンテナーの詳細については、「 [ C++標準ライブラリコンテナー](../standard-library/stl-containers.md)」を参照してください。

## <a name="see-also"></a>関連項目

[C++ へようこそ (Modern C++)](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ 言語リファレンス](../cpp/cpp-language-reference.md)<br/>
[.NET 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)
