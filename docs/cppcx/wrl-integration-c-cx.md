---
title: WRL 統合 (C++/CX)
ms.date: 01/22/2017
ms.assetid: 3ad43894-c574-477c-ad3e-240301f381d4
ms.openlocfilehash: 3ea0f6aece985a2ee74916e737b9aab1bf0d1d96
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91507409"
---
# <a name="wrl-integration-ccx"></a>WRL 統合 (C++/CX)

WRL コードと Windows ランタイム C++ テンプレートライブラリ (WRL) コードを自由に混在させることができます。 同じ翻訳単位で、WRL handle to object ( `^` ) 表記および wrl スマートポインター () 表記で宣言されたオブジェクトを使用でき `ComPtr<T>` ます。 ただし、戻り値、WRL HRESULT エラーコード、および WRL 例外を手動で処理する必要があります。

## <a name="wrl-development"></a>WRL 開発

WRL コンポーネントの作成と使用の詳細については、「 [Windows ランタイム C++ テンプレートライブラリ (wrl)](./wrl/windows-runtime-cpp-template-library-wrl.md)」を参照してください。

### <a name="example"></a>例

次のコードスニペットは、WRL と WRL を使用して Windows ランタイムクラスを使用し、メタデータファイルを調べる方法を示しています。

この例は、Microsoft Store アプリの構築フォーラムのコードスニペットから取得されています。 このコード スニペットの作成者は、次の免責条項と条件を提示しています。

1. C++ は Windows ランタイム型に対してリフレクションする特定の Api を提供していませんが、型の Windows メタデータファイル (winmd) は CLR メタデータファイルに完全に準拠しています。 Windows は、指定された型の .winmd ファイルを取得するために新しいメタデータ検出 API (RoGetMetaDataFile) を提供しています。 ただし、クラスをインスタンス化できないため、これらの API は C++ 開発者にはあまり役に立ちません。

1. コードをコンパイルした後、Runtimeobject.lib と Rometadata.lib をリンカーに渡す必要もあります。

1. このスニペットは現状のままで示されています。 正しく動作すると予測されますが、エラーが含まれている可能性もあります。

```cpp
#include <hstring.h>
#include <cor.h>
#include <rometadata.h>
#include <rometadataresolution.h>
#include <collection.h>

namespace ABI_Isolation_Workaround {
    #include <inspectable.h>
    #include <WeakReference.h>
}
using namespace ABI_Isolation_Workaround;
#include <wrl/client.h>

using namespace Microsoft::WRL;
using namespace Windows::Foundation::Collections;

IVector<String^>^ GetTypeMethods(Object^);

MainPage::MainPage()
{
    InitializeComponent();

    Windows::Foundation::Uri^ uri = ref new Windows::Foundation::Uri("http://buildwindows.com/");
    auto methods = GetTypeMethods(uri);

    std::wstring strMethods;
    std::for_each(begin(methods), end(methods), [&strMethods](String^ methodName) {
        strMethods += methodName->Data();
        strMethods += L"\n";
    });

    wprintf_s(L"%s\n", strMethods.c_str());
}

IVector<String^>^ GetTypeMethods(Object^ instance)
{
    HRESULT hr;
    HSTRING hStringClassName;
    hr = instance->__cli_GetRuntimeClassName(reinterpret_cast<__cli_HSTRING__**>(&hStringClassName)); // internal method name subject to change post BUILD
    if (FAILED(hr))
        __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD
    String^ className = reinterpret_cast<String^>(hStringClassName);

    ComPtr<IMetaDataDispenserEx> metadataDispenser; ComPtr<IMetaDataImport2> metadataImport; hr = MetaDataGetDispenser(CLSID_CorMetaDataDispenser, IID_IMetaDataDispenser, (LPVOID*)metadataDispenser.GetAddressOf());
    if (FAILED(hr))
        __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD

    HSTRING hStringFileName;
    mdTypeDef typeDefToken;
    hr = RoGetMetaDataFile(hStringClassName, metadataDispenser.Get(), &hStringFileName, &metadataImport, &typeDefToken);
    if (FAILED(hr))
        __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD
    String^ fileName = reinterpret_cast<String^>(hStringFileName);

    HCORENUM hCorEnum = 0;
    mdMethodDef methodDefs[2048];
    ULONG countMethodDefs = sizeof(methodDefs);
    hr = metadataImport->EnumMethods(&hCorEnum, typeDefToken, methodDefs, countMethodDefs,  &countMethodDefs);
    if (FAILED(hr))
        __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD

    wchar_t methodName[1024];
    ULONG countMethodName;
    std::wstring strMethods;
    Vector<String^>^ retVal = ref new Vector<String^>();

    for (int i = 0; i < countMethodDefs; ++i)
    {
        countMethodName = sizeof(methodName);
        hr = metadataImport->GetMethodProps(methodDefs[i], nullptr, methodName, countMethodName, &countMethodName, nullptr, nullptr, nullptr, nullptr, nullptr);
        if (SUCCEEDED(hr))
        {
            methodName[ countMethodName ] = 0;
            retVal->Append(ref new String(methodName));
        }
    }
    return retVal;
}
```

## <a name="see-also"></a>関連項目

[他の言語との相互運用](interoperating-with-other-languages-c-cx.md)
