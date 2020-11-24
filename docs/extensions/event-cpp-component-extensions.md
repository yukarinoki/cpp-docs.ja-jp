---
title: event キーワード (C++/CLI および C++/CX)
description: Microsoft C++ コンポーネント拡張キーワードを使用する方法について説明 `event` します。
ms.date: 11/20/2020
ms.topic: reference
f1_keywords:
- event
- event_cpp
helpviewer_keywords:
- event keyword [C++]
ms.openlocfilehash: 6a2fa97140f747b4afc380b57f8f7c71f08875db
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483244"
---
# <a name="event-keyword-ccli-and-ccx"></a>`event` キーワード (C++/CLI および C++/CX)

キーワードは、 **`event`** 関心のあるものが発生した登録サブスクライバー (*イベントハンドラー*) への通知である *イベント* を宣言します。

## <a name="all-runtimes"></a>すべてのランタイム

C++/CX では、"*イベント メンバー*" または "*イベント ブロック*" の宣言がサポートされます。 イベント メンバーは、イベント ブロックを宣言する簡単な表記法です。 既定ではイベント メンバーは、イベント ブロックで明示的に宣言される、`add` 関数、`remove` 関数、および `raise` 関数を宣言します。 イベント メンバーの関数をカスタマイズするには、イベント ブロックを宣言した後で必要な関数をオーバーライドします。

### <a name="syntax"></a>構文

```cpp
// event data member
modifier event delegate^ event_name;

// event block
modifier event delegate^ event_name
{
   modifier return_value add(delegate^ name);
   modifier void remove(delegate^ name);
   modifier void raise(parameters);
}
```

### <a name="parameters"></a>パラメーター

*変換*\
イベントの宣言またはイベントのアクセサー メソッドで使用できる修飾子。  指定できる値は **`static`** 、および **`virtual`** です。

*人*\
[デリゲート](delegate-cpp-component-extensions.md)。このデリゲートのシグネチャがイベント ハンドラーと一致する必要があります。

*event_name*\
イベントの名前です。

*return_value*\
イベントのアクセサー メソッドの戻り値。  検証可能にするには、戻り値の型がである必要があり **`void`** ます。

*パラメータ*\
(省略可能) *delegate* パラメーターのシグネチャと一致する、`raise` メソッドのパラメーター。

### <a name="remarks"></a>注釈

イベントは、デリゲートと *イベントハンドラー* の間の関連付けです。 イベントハンドラーは、イベントがトリガーされたときに応答するメンバー関数です。 これにより、任意のクラスのクライアントが、デリゲートのシグネチャと戻り値の型に一致するメソッドを登録できるようになります。

イベントの宣言には 2 つの種類があります。

*イベントデータメンバー*\
コンパイラが自動的にデリゲート型のメンバーの形でイベント用のストレージを作成し、内部の `add`、`remove`、および `raise` の各メンバー関数を作成します。 イベント データ メンバーはクラス内で宣言する必要があります。 デリゲートの戻り値の型と、イベント ハンドラーの戻り値の型が一致する必要があります。

*イベントブロック*\
イベント ブロックを使用して、`add`、`remove`、および `raise` の各メソッドの動作を明示的に宣言し、カスタマイズすることができます。

およびを使用して `operator +=` `operator -=` 、イベントハンドラーを追加および削除したり、 `add` メソッドとメソッドを明示的に呼び出したりすることができ `remove` ます。

**`event`** は、状況依存のキーワードです。 詳細については、「 [状況依存のキーワード](context-sensitive-keywords-cpp-component-extensions.md)」を参照してください。

## <a name="windows-runtime"></a>Windows ランタイム

### <a name="remarks"></a>注釈

詳細については、「[イベント (C++/CX)](../cppcx/events-c-cx.md)」を参照してください。

イベントハンドラーを追加して後で削除するには、 `EventRegistrationToken` 操作によって返される構造体を保存し `add` ます。 次に、操作で、保存された構造体を使用して、 `remove` `EventRegistrationToken` 削除するイベントハンドラーを識別します。

### <a name="requirements"></a>必要条件

コンパイラ オプション: `/ZW`

## <a name="common-language-runtime"></a>共通言語ランタイム

**event** キーワードを使用して、イベントを宣言できます。 イベントは、何か重要なことが起きたときにクラスで通知するための手段です。

### <a name="syntax"></a>構文

```cpp
// event data member
modifier event delegate^ event_name;

// event block
modifier event delegate^ event_name
{
   modifier return_value add(delegate^ name);
   modifier void remove(delegate^ name);
   modifier void raise(parameters);
}
```

### <a name="parameters"></a>パラメーター

*変換*\
イベントの宣言またはイベントのアクセサー メソッドで使用できる修飾子。  指定できる値は **`static`** 、および **`virtual`** です。

*人*\
[デリゲート](delegate-cpp-component-extensions.md)。このデリゲートのシグネチャがイベント ハンドラーと一致する必要があります。

*event_name*\
イベントの名前です。

*return_value*\
イベントのアクセサー メソッドの戻り値。  検証可能にするには、戻り値の型がである必要があり **`void`** ます。

*パラメータ*\
(省略可能) *delegate* パラメーターのシグネチャと一致する、`raise` メソッドのパラメーター。

### <a name="remarks"></a>注釈

イベントは、デリゲートと *イベントハンドラー* の間の関連付けです。 イベントハンドラーは、イベントがトリガーされたときに応答するメンバー関数です。 これにより、任意のクラスのクライアントが、基になるデリゲートのシグネチャと戻り値の型に一致するメソッドを登録できるようになります。

デリゲートには、1つ以上のメソッドを関連付けることができます。 これらのメソッドは、イベントが発生したことをコードが示すときに呼び出されます。 プログラム内のイベントを、.NET Framework 共通言語ランタイムを対象とする他のプログラムで使用できるようにすることができます。

イベント宣言には、次の2種類があります。

*イベントデータメンバー*\
コンパイラは、データメンバーイベントのストレージをデリゲート型のメンバーとして作成します。 イベント データ メンバーはクラス内で宣言する必要があります。 これは、 *単純なイベント* とも呼ばれます。 例については、コードサンプルを参照してください。

*イベントブロック*\
イベントブロックを使用すると、、、およびの各メソッドを実装することで、、、およびの各メソッドの動作をカスタマイズでき `add` `remove` `raise` `add` `remove` `raise` ます。 `add`、、およびメソッドのシグネチャは、 `remove` `raise` デリゲートのシグネチャと一致する必要があります。 イベントブロックイベントはデータメンバーではありません。 データメンバーとして使用すると、コンパイラエラーが生成されます。

イベント ハンドラーの戻り値の型は、デリゲートの戻り値の型と一致する必要があります。

.NET Framework では、それ自身がメソッド (つまり、対応するデリゲートの `Invoke` メソッド) であるかのようにデータ メンバーを処理できます。 これを行うには、マネージイベントデータメンバーを宣言するためのデリゲート型を事前に定義します。 これに対し、マネージイベントメソッドは、まだ定義されていない場合は、対応するマネージデリゲートを暗黙的に定義します。 例については、この記事の最後にあるコードサンプルを参照してください。

マネージイベントを宣言するときに、 `add` `remove` 演算子とを使用してイベントハンドラーが追加または削除されたときに呼び出されるアクセサーとアクセサーを指定でき **`+=`** **`-=`** ます。 `add`、、およびの各メソッドは、 `remove` `raise` 明示的に呼び出すことができます。

Microsoft C++ でイベントを作成して使用するには、次の手順を実行する必要があります。

1. デリゲートを作成または指定します。 独自のイベントを定義する場合は、キーワードと共に使用するデリゲートが存在することも確認する必要があり **`event`** ます。 イベントが .NET Framework などで事前に定義されている場合、そのイベントのコンシューマーにはデリゲートの名前を指定するだけでかまいません。

2. 次のものを含むクラスを作成します。

   - デリゲートから作成されるイベント。

   - Optionalキーワードで宣言されたデリゲートのインスタンスが存在することを確認するメソッド **`event`** 。 省略する場合、イベントを発生させるコード内にこのロジックを組み込む必要があります。

   - イベントを呼び出すメソッド。 このメソッドは一部の基本クラスの機能によってオーバーライドされる場合があります。

   このクラスでイベントを定義します。

3. メソッドをイベントに接続するクラスを 1 つ以上定義します。 それぞれのクラスで、1 つ以上のメソッドを基本クラスのイベントと関連付けます。

4. イベントを使用します。

   - イベントの宣言を含むクラスのオブジェクトを作成します。

   - イベントの定義を含むクラスのオブジェクトを作成します。

C++/CLI イベントの詳細については、「 [インターフェイスのイベント](../dotnet/how-to-use-events-in-cpp-cli.md)」を参照してください。

### <a name="requirements"></a>必要条件

コンパイラ オプション: `/clr`

### <a name="examples"></a>例

次のコード例は、デリゲート、イベント、およびイベントハンドラーのペアの宣言を示しています。 イベントハンドラーをサブスクライブ (追加) し、呼び出し、サブスクライブ解除 (削除) する方法を示します。

```cpp
// mcppv2_events.cpp
// compile with: /clr
using namespace System;

// declare delegates
delegate void ClickEventHandler(int, double);
delegate void DblClickEventHandler(String^);

// class that defines events
ref class EventSource {
public:
   event ClickEventHandler^ OnClick;   // declare the event OnClick
   event DblClickEventHandler^ OnDblClick;   // declare OnDblClick

   void FireEvents() {
      // raises events
      OnClick(7, 3.14159);
      OnDblClick("Hello");
   }
};

// class that defines methods that will called when event occurs
ref class EventReceiver {
public:
   void OnMyClick(int i, double d) {
      Console::WriteLine("OnClick: {0}, {1}", i, d);
   }

   void OnMyDblClick(String^ str) {
      Console::WriteLine("OnDblClick: {0}", str);
   }
};

int main() {
   EventSource ^ MyEventSource = gcnew EventSource();
   EventReceiver^ MyEventReceiver = gcnew EventReceiver();

   // hook handler to event
   MyEventSource->OnClick += gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);
   MyEventSource->OnDblClick += gcnew DblClickEventHandler(MyEventReceiver, &EventReceiver::OnMyDblClick);

   // invoke events
   MyEventSource->FireEvents();

   // unhook handler to event
   MyEventSource->OnClick -= gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);
   MyEventSource->OnDblClick -= gcnew DblClickEventHandler(MyEventReceiver, &EventReceiver::OnMyDblClick);
}
```

```Output
OnClick: 7, 3.14159

OnDblClick: Hello
```

次のコード例は、単純なイベントのメソッドを生成するために使用されるロジックを示して `raise` います。 イベントに 1 つまたは複数のサブスクライバーが含まれている場合は、`raise` メソッドを呼び出すと、デリゲートが暗黙的または明示的に呼び出されます。 デリゲートの戻り値の型がではなく、 **`void`** イベントサブスクライバーがゼロの場合、 `raise` メソッドはデリゲート型の既定値を返します。 イベントサブスクライバーが存在しない場合、メソッドを呼び出す `raise` とすぐにが返され、例外は発生しません。 デリゲートの戻り値の型がでない場合は、 **`void`** デリゲート型が返されます。

```cpp
// trivial_events.cpp
// compile with: /clr /c
using namespace System;
public delegate int Del();
public ref struct C {
   int i;
   event Del^ MyEvent;

   void FireEvent() {
      i = MyEvent();
   }
};

ref struct EventReceiver {
   int OnMyClick() { return 0; }
};

int main() {
   C c;
   c.i = 687;

   c.FireEvent();
   Console::WriteLine(c.i);
   c.i = 688;

   EventReceiver^ MyEventReceiver = gcnew EventReceiver();
   c.MyEvent += gcnew Del(MyEventReceiver, &EventReceiver::OnMyClick);
   Console::WriteLine(c.i);
}
```

```Output
0

688
```

## <a name="see-also"></a>関連項目

[.NET および UWP 用のコンポーネント拡張](component-extensions-for-runtime-platforms.md)
