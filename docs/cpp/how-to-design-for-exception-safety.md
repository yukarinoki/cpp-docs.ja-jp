---
title: 'How to: Design for exception safety'
ms.custom: how-to
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: 19ecc5d4-297d-4c4e-b4f3-4fccab890b3d
ms.openlocfilehash: 48a2f5a94eb2695c0a08a0ae397d02080e7e1261
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246516"
---
# <a name="how-to-design-for-exception-safety"></a>How to: Design for exception safety

例外機構の利点の 1 つは、例外をスローするステートメントから例外を処理する最初の catch ステートメントに、例外に関するデータと共に実行が直接ジャンプすることです。 ハンドラーは呼び出し履歴の何レベル上であってもかまいません。 try ステートメントと throw ステートメントの間で呼び出された関数は、スローされる例外に関して何も知る必要がありません。  ただし、例外が下から上に通知される可能性があるどの時点でも、予期せずにスコープから外れることができるように関数が設計されている必要があり、部分的に作成されたオブジェクト、リークしたメモリ、使用不能な状態のデータ構造体などが部分的に残らないようになっている必要があります。

## <a name="basic-techniques"></a>Basic techniques

堅牢な例外処理ポリシーには、熟考が必要であり、デザイン プロセスの一部になっている必要があります。 一般に、ほとんどの例外は、ソフトウェア モジュールの下位層で検出されてスローされますが、一般にこれらの層には、エラーを処理したり、エンド ユーザーにメッセージを通知するための十分なコンテキストがありません。 中間層の関数は、例外オブジェクトを検査する必要があったり、最終的に例外をキャッチする上位層のための有用な追加情報がある場合に、例外をキャッチして再スローできます。 関数が例外をキャッチしてそれを "飲み込む" ことができるのは、例外から完全に回復できる場合のみです。 多くの場合、中間層の正しい動作は、呼び出し履歴の上方向へ例外を伝達することです。 最上位層でも、例外によってプログラムがその正しさを保証できない状態になる場合は、例外を処理せずにプログラムを終了するのが適切な場合があります。

関数が例外を処理する方法にかかわらず、"例外セーフ" であることを保証するには、次の基本的なルールに従って関数が設計されている必要があります。

### <a name="keep-resource-classes-simple"></a>Keep resource classes simple

When you encapsulate manual resource management in classes, use a class that does nothing except manage a single resource. By keeping the class simple, you reduce the risk of introducing resource leaks. Use [smart pointers](smart-pointers-modern-cpp.md) when possible, as shown in the following example. この例は、`shared_ptr` を使用した場合の相違点を強調するため、意図的に作成し簡略化されています。

```cpp
// old-style new/delete version
class NDResourceClass {
private:
    int*   m_p;
    float* m_q;
public:
    NDResourceClass() : m_p(0), m_q(0) {
        m_p = new int;
        m_q = new float;
    }

    ~NDResourceClass() {
        delete m_p;
        delete m_q;
    }
    // Potential leak! When a constructor emits an exception,
    // the destructor will not be invoked.
};

// shared_ptr version
#include <memory>

using namespace std;

class SPResourceClass {
private:
    shared_ptr<int> m_p;
    shared_ptr<float> m_q;
public:
    SPResourceClass() : m_p(new int), m_q(new float) { }
    // Implicitly defined dtor is OK for these members,
    // shared_ptr will clean up and avoid leaks regardless.
};

// A more powerful case for shared_ptr

class Shape {
    // ...
};

class Circle : public Shape {
    // ...
};

class Triangle : public Shape {
    // ...
};

class SPShapeResourceClass {
private:
    shared_ptr<Shape> m_p;
    shared_ptr<Shape> m_q;
public:
    SPShapeResourceClass() : m_p(new Circle), m_q(new Triangle) { }
};
```

### <a name="use-the-raii-idiom-to-manage-resources"></a>Use the RAII idiom to manage resources

To be exception-safe, a function must ensure that objects that it has allocated by using `malloc` or **new** are destroyed, and all resources such as file handles are closed or released even if an exception is thrown. The *Resource Acquisition Is Initialization* (RAII) idiom ties management of such resources to the lifespan of automatic variables. 正常に返るか例外により関数がスコープから外れた場合、すべての完全構築された自動変数のデストラクターが呼び出されます。 スマート ポインターなどの RAII ラッパー オブジェクトは、デストラクターの中で適切な delete または close 関数を呼び出します。 例外セーフなコードでは、なんらかの種類の RAII オブジェクトに各リソースの所有権をすぐに渡すことが非常に重要です。 Note that the `vector`, `string`, `make_shared`, `fstream`, and similar classes handle acquisition of the resource for you.  However, `unique_ptr` and traditional `shared_ptr` constructions are special because resource acquisition is performed by the user instead of the object; therefore, they count as *Resource Release Is Destruction* but are questionable as RAII.

## <a name="the-three-exception-guarantees"></a>The three exception guarantees

Typically, exception safety is discussed in terms of the three exception guarantees that a function can provide: the *no-fail guarantee*, the *strong guarantee*, and the *basic guarantee*.

### <a name="no-fail-guarantee"></a>No-fail guarantee

no-fail (または no-throw) 保証は、関数が提供できる最も強力な保証です。 それは、関数が例外をスローしないか、例外の伝達を許可することを示します。 ただし、(a) この関数が呼び出すすべての関数が no-fail であることがわかっているか、(b) スローされるすべての例外がこの関数に達する前にキャッチされることがわかっているか、(c) この関数に達する可能性があるすべての例外をキャッチし正しく処理する方法がわかっている場合を除いて、確実にこのようなことを保証できません。

strong 保証と basic 保証のどちらも、デストラクターが no-fail であることを前提としています。 標準ライブラリのすべてのコンテナーと型は、デストラクターが例外をスローしないことを保証します。 また、逆の要件もあります。標準ライブラリでは、テンプレート引数として渡される型など、ユーザー定義型のデストラクターが、例外をスローしないことが必要です。

### <a name="strong-guarantee"></a>Strong guarantee

strong 保証は、関数が例外によりスコープから外れる場合、メモリをリークせず、プログラムの状態が変化しないことを示します。 strong 保証を提供する関数は、基本的にコミットまたはロールバック セマンティクスを持つトランザクションです。つまり、完全に成功するか無効かのどちらかになります。

### <a name="basic-guarantee"></a>Basic guarantee

basic 保証は、3 つのうちで最も弱い保証です。 ただし、strong 保証がメモリ消費またはパフォーマンスの点で高価すぎる場合に最善の選択肢となる場合があります。 basic 保証は、例外が発生した場合は、データが変更された可能性があるとしても、メモリがリークせず、オブジェクトが引き続き使用可能な状態にあることを示します。

## <a name="exception-safe-classes"></a>Exception-safe classes

クラスは、安全でない関数で使用される場合であっても、自身が部分的に構築されたり部分的に破棄されるのを防ぐことにより、自身の例外セーフ性を保証するのに役立つことがあります。 クラス コンストラクターが完了前に終了した場合、オブジェクトは作成されず、そのデストラクターは決して呼び出されません。 例外の前に初期化された自動変数のデストラクターは呼び出されますが、動的に割り当てられたメモリや、スマート ポインターなどの自動変数によって管理されていないリソースはリークすることになります。

組み込みの型はすべて no-fail であり、標準ライブラリの型は少なくとも basic 保証をサポートしています。 例外セーフである必要があるすべてのユーザー定義型について、次のガイドラインに従ってください。

- スマート ポインターまたは他の RAII 型ラッパーを使用してすべてのリソースを管理します。 コンストラクターが例外をスローするとデストラクターが起動されないので、クラスのデストラクターにリソース管理機能を持たせないようにします。 ただし、クラスが 1 種類のリソースのみを制御する専用のリソース マネージャーである場合は、デストラクターを使用してリソースを管理してもかまいません。

- 基底クラスのコンストラクターでスローされる例外は、派生クラスのコンストラクターで飲み込むことができない点に注意します。 基底クラスの例外を派生クラスのコンストラクターで変換して再スローする場合は、関数の try ブロックを使用します。

- 特に、クラスに "失敗することが可能な初期化" の概念がある場合は、すべてのクラス状態を、スマート ポインターでラップされたデータ メンバーに保存するかどうかを検討します。 C++ では初期化されていないデータ メンバーが許可されていますが、初期化されていないか部分的に初期化されたクラス インスタンスはサポートされていません。 コンストラクターは成功または失敗のいずれかであることが必要です。コンストラクターが最後まで実行されない場合、オブジェクトは作成されません。

- デストラクターから例外が漏れないようにします。 C++ の基本的な原則は、デストラクターで例外が呼び出し履歴の上方向へ伝達されないようにすることです。 デストラクターで例外をスローする可能性がある操作を実行する必要がある場合は、try catch ブロックで実行し、例外を飲み込む必要があります。 標準ライブラリでは、定義されているすべてのデストラクターでこのことが保証されます。

## <a name="see-also"></a>関連項目

[Modern C++ best practices for exceptions and error handling](errors-and-exception-handling-modern-cpp.md)<br/>
[方法: 例外的なコードと非例外的なコードをインターフェイスで連結する](how-to-interface-between-exceptional-and-non-exceptional-code.md)
