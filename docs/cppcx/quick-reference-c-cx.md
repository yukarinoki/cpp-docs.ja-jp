---
title: クイック リファレンス (C + + CX) |Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: ba457195-26e5-43aa-b99d-24a871e550f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 272921d0a9ac00ec5ee69fb50a17a34e257b1725
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43692589"
---
# <a name="quick-reference-ccx"></a>クイック リファレンス (C++/CX)
Windows ランタイムでは、信頼できるオペレーティング システム環境でのみ実行し、承認済みの関数、データ型、およびデバイスを使用して、Microsoft Store で配布されてユニバーサル Windows プラットフォーム (UWP) アプリをサポートします。 C++/cli CX の Windows ランタイム アプリの作成を簡略化します。 この記事では、クイック リファレンスです。詳細なドキュメントは、次を参照してください。[型システム](../cppcx/type-system-c-cx.md)します。  
  
 コマンドラインでビルドするときに使用して、 **/ZW**コンパイラ オプションを UWP アプリまたは Windows ランタイム コンポーネントをビルドします。 Windows ランタイム メタデータ (.winmd) ファイルで定義されている Windows ランタイムの宣言にアクセスする指定、`#using`ディレクティブまたは **/FU**コンパイラ オプション。 UWP アプリ用のプロジェクトを作成するときに、既定では、Visual Studio はこれらのオプションを設定し、すべての Windows ランタイム ライブラリへの参照を追加します。  
  
## <a name="quick-reference"></a>クイック リファレンス  
  
|概念|標準 C++|C++/CX|Remarks|  
|-------------|--------------------|------------------------------------------------------------------|-------------|  
|基本的な型|C++ の基本型。|C + + CX 基本型、Windows ランタイムで定義されている基本的な型を実装します。|`default`名前空間を含む C +/cli CX の組み込みの基本型。 コンパイラは暗黙的にマップ C +/cli 標準 C++ 型に CX 基本型。<br /><br /> `Platform`ファミリ名前空間のには基本的な Windows ランタイム型を実装する型が含まれています。|  
||`bool`|`bool`|8 ビットのブール値。|  
||`__wchar_t`|`char16`|Unicode (UTF-16) コード ポイントを表す 16 ビットの数字以外の値。|  
||`short`<br /><br /> `unsigned short`|`int16`<br /><br /> `uint16`|16 ビット符号付き整数。<br /><br /> 16 ビット符号なし整数。|  
||`int`<br /><br /> `unsigned int`|`int`<br /><br /> `uint32`|32 ビット符号付き整数。<br /><br /> 32 ビット符号なし整数|  
||`long long` または `__int64`<br /><br /> `unsigned long long`|`int64`<br /><br /> `uint64`|64 ビット符号付き整数。<br /><br /> 64 ビット符号なし整数。|  
||`float, double`|`float32, float64`|32 ビットまたは 64 ビットの IEEE 754 浮動小数点数。|  
||`enum {}`|`enum class {}`<br /><br /> - または -<br /><br /> `enum struct {}`|32 ビット列挙体。|  
||(該当なし)|`Platform::Guid`|`Platform` 名前空間での 128 ビット非数値 (GUID)。|  
||`std::time_get`|`Windows::Foundation::DateTime`|日付と時刻の構造体。|  
||(該当なし)|`Windows::Foundation::TimeSpan`|期間の構造体。|  
||(該当なし)|`Platform::Object^`|参照カウントのベース オブジェクト型システムは Windows ランタイム C++ ビュー。|  
||`std::wstring`<br /><br /> `L"..."`|`Platform::String^`|`Platform::String^` は、テキストを表す Unicode 文字列の、参照がカウントされて変更不可能なシーケンスです。|  
|ポインター|オブジェクトへのポインター (`*`):<br /><br /> `std::shared_ptr`|オブジェクトへのハンドル (`^`、「ハット」と発音):<br /><br /> *T^ identifier*|すべての Windows ランタイム クラスは、オブジェクトへのハンドル修飾子を使用して宣言されます。 オブジェクトのメンバーにアクセスするには、矢印 (`->`) クラス メンバー アクセス演算子を使用します。<br /><br /> ハット修飾子は「自動的に参照される Windows ランタイム オブジェクトへのポインターがカウントされます」 より厳密には、オブジェクトへのハンドルは、コンパイラが、オブジェクトの参照カウントを自動的に管理するためのコードを挿入する必要があること、および参照カウントがゼロになった場合にオブジェクトを削除する必要があることを宣言します。|  
|参照|オブジェクトへの参照 (`&`):<br /><br /> *T* `&` *identifier*|トラッキング参照 (`%`):<br /><br /> *T* `%` *identifier*|修飾子を参照する唯一の Windows ランタイム型は、追跡を使用して宣言できます。 オブジェクトのメンバーにアクセスするには、ドット (`.`) クラス メンバー アクセス演算子を使用します。<br /><br /> 追跡参照は「への参照カウントされた参照で自動的にある Windows ランタイム オブジェクト」 より厳密には、追跡参照は、コンパイラが、オブジェクトの参照カウントを自動的に管理するためのコードを挿入する必要があること、および参照カウントがゼロになった場合にオブジェクトを削除する必要があることを宣言します。|  
|動的な型の宣言|`new`|`ref new`|Windows ランタイム オブジェクトを割り当てるし、そのオブジェクトへのハンドルを返します。|  
|オブジェクトの有効期間の管理|`delete` *identifier*<br /><br /> `delete[]`  *identifier*|(デストラクターを呼び出します。)|有効期間は、参照カウントによって決まります。 削除への呼び出しはデストラクターを呼び出しますが、それ自体はメモリを解放しません。|  
|配列の宣言|*T  identifier* `[]`<br /><br /> `std::array` *identifier*|`Array<` *T* `^>^` *identifier* `(` *size* `)`<br /><br /> - または -<br /><br /> `WriteOnlyArray<` *T* `^>`  *identifier* `(` *size* `)`|T^ 型の、1 次元変更可能または書き込み専用の配列を宣言します。 配列自体も、オブジェクトへのハンドル修飾子を使用して宣言する必要がある、参照カウント オブジェクトです。<br /><br /> (配列宣言は、 `Platform` 名前空間にあるヘッダー テンプレート クラスを使用します。)|  
|クラス宣言|`class`  *identifier* `{}`<br /><br /> `struct` *identifier* `{}`|`ref class` *identifier* `{}`<br /><br /> `ref struct` *identifier* `{}`|既定のプライベート アクセシビリティを持つランタイム クラスを宣言します。<br /><br /> 既定のパブリック アクセシビリティを持つランタイム クラスを宣言します。|  
|構造体宣言|`struct` *identifier* `{}`<br /><br /> (つまり、PODS (Plain Old Data Structure))|`value class` *identifier* `{}`<br /><br /> `value struct` *identifier* `{}`|既定のプライベート アクセシビリティを持つ POD 構造体を宣言します。<br /><br /> 値のクラスは Windows メタデータで表現できますが、標準の C++ クラスは Windows メタデータで表現できません。<br /><br /> 既定のパブリック アクセシビリティを持つ POD 構造体を宣言します。<br /><br /> 値の構造体は Windows メタデータで表現できますが、標準 C++ 構造体は Windows メタデータで表現できません。|  
|インターフェイス宣言|純粋仮想関数のみを含む抽象クラス。|`interface class` *identifier* `{}`<br /><br /> `interface struct` *identifier* `{}`|既定のプライベート アクセシビリティを持つインターフェイスを宣言します。<br /><br /> 既定のパブリック アクセシビリティを持つインターフェイスを宣言します。|  
|delegate|`std::function`|`public delegate` *return-type* *delegate-type-identifier* `(` *[ parameters ]* `);`|関数呼び出しのように呼び出すことができるオブジェクトを宣言します。|  
|event|(該当なし)|`event` *delegate-type-identifier* *event-identifier* `;`<br /><br /> *delegate-type-identifier* *delegate-identifier* = `ref new`*delegate-type-identifier*`( this`*[, parameters]*`);`<br /><br /> *event-identifier* `+=` *delegate-identifier* `;`<br /><br /> - または -<br /><br /> `EventRegistrationToken` *token-identifier* = *obj*`.`*event-identifier*`+=`*delegate-identifier*`;`<br /><br /> - または -<br /><br /> `auto` *トークン識別子* = *obj*します。*イベント識別子*`::add(`*デリゲート識別子*`);`<br /><br /> *obj* `.` *event-identifier* `-=` *token-identifier* `;`<br /><br /> - または -<br /><br /> *obj* `.` *event-identifier* `::remove(` *token-identifier* `);`|イベント オブジェクトを宣言し、そこにイベントが発生したときに呼び出されるイベント ハンドラー (デリゲート) のコレクションを格納します。<br /><br /> イベント ハンドラーを作成します。<br /><br /> イベント ハンドラーを追加します。<br /><br /> イベント ハンドラーを追加すると、イベント トークン (*token-identifier*) が返されます。 明示的にイベント ハンドラーを削除することを意図している場合は、後で使用できるようにイベント トークンを保存する必要があります。<br /><br /> イベント ハンドラーを削除します。<br /><br /> イベント ハンドラーを削除するには、イベント ハンドラーが追加されたときに保存したイベント トークンを指定する必要があります。|  
|property|(該当なし)|`property` *T* *identifier*;<br /><br /> `property` *T* *identifier* `[` *インデックス* `];`<br /><br /> `property` *T* `default[` *インデックス* `];`|クラス メンバー関数またはオブジェクト メンバー関数が、データ メンバーまたはインデックス付きの配列要素へのアクセスで使用されたのと同じ構文を使用してアクセスされることを宣言します。<br /><br /> クラス オブジェクト メンバー関数またはオブジェクト メンバー関数のインデックス付きプロパティを宣言します。<br /><br /> オブジェクト メンバー関数のインデックス付きプロパティを宣言します。<br /><br /> クラス メンバー関数のインデックス付きプロパティを宣言します。|  
|パラメーター化された型|テンプレート|`generic <typename` *T* `> interface class` *identifier* `{}`<br /><br /> `generic <typename` *T* `> delegate` *[return-type]* *delegate-identifier* `() {}`|パラメーター化されたインターフェイス クラスを宣言します。<br /><br /> パラメーター化されたデリゲートを宣言します。|  
|null 許容値型|`boost::optional<T>`|[Platform::ibox \<T >](../cppcx/platform-ibox-interface.md)|スカラー型および値構造体の変数の値を `nullptr`にすることができます。|  
  
## <a name="see-also"></a>関連項目  
 [Visual C 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)