---
title: 'TN059: MFC MBCS-Unicode 変換マクロの使用'
ms.date: 11/04/2016
helpviewer_keywords:
- MFCANS32.DLL
- Unicode [MFC], conversion macros
- Unicode [MFC], OLE interfaces
- conversion macros [MFC]
- converting Unicode
- MBCS [MFC], conversion macros
- macros [MFC], MBCS conversion macros
- TN059
ms.assetid: a2aab748-94d0-4e2f-8447-3bd07112a705
ms.openlocfilehash: 657381d8247aef14b2c725996dfeb11d0e0535fe
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749435"
---
# <a name="tn059-using-mfc-mbcsunicode-conversion-macros"></a>テクニカル ノート 59: MFC の MBCS/Unicode 変換マクロの使用

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

この資料では、AFXPRIV で定義されている MBCS/Unicode 変換のマクロを使用する方法について説明します。H。 これらのマクロは、アプリケーションが OLE API を直接処理する場合や、何らかの理由で Unicode と MBCS の間で変換する必要がある場合に最も役立ちます。

## <a name="overview"></a>概要

MFC 3.x では、特別な DLL が使用されました (MFCANS32.DLL) は、OLE インターフェイスが呼び出されたときに、Unicode と MBCS の間で自動的に変換します。 この DLL は、OLE API とインターフェイスが常に Unicode である場合でも (Macintosh を除く) として OLE アプリケーションを記述できる、ほとんど透過的な層でした。 このレイヤーは便利で、アプリケーションを Win16 から Win32 (MFC、Microsoft Word、Excel、および VBA) にすばやく移植することができましたが、このテクノロジを使用したマイクロソフトのアプリケーションの一部に過ぎませんでしたが、パフォーマンスに大きな影響を与えることがありました。 このため、MFC 4.x はこの DLL を使用せず、代わりに Unicode OLE インターフェイスと直接話します。 これを行うには、MFC は、OLE インターフェイスを呼び出すときに Unicode から MBCS に変換する必要があり、多くの場合、OLE インターフェイスを実装するときに、Unicode から MBCS に変換する必要があります。 これを効率的かつ簡単に処理するために、この変換を容易にするために多数のマクロが作成されました。

このようなマクロセットを作成する最大のハードルの 1 つは、メモリの割り当てです。 文字列を所定の位置に変換できないため、変換された結果を保持する新しいメモリを割り当てる必要があります。 これは、次のようなコードで行う可能性があります。

```
// we want to convert an MBCS string in lpszA
int nLen = MultiByteToWideChar(CP_ACP,
    0,
    lpszA, -1,
    NULL,
    NULL);

LPWSTR lpszW = new WCHAR[nLen];
MultiByteToWideChar(CP_ACP,
    0,
    lpszA, -1,
    lpszW,
    nLen);

// use it to call OLE here
pI->SomeFunctionThatNeedsUnicode(lpszW);

// free the string
delete[] lpszW;
```

このアプローチは、いくつかの問題として。 主な問題は、書き込み、テスト、デバッグが多いという点です。 単純な関数呼び出しだったものは、今でははるかに複雑です。 また、実行時のオーバーヘッドが大きくなります。 メモリはヒープに割り当てられ、変換が完了するたびに解放される必要があります。 最後に、上記のコードは、Unicode`#ifdefs`と Macintosh ビルドに適切に追加する必要があります (この変換を行う必要はありません)。

私たちが考え出した解決策は、1)様々なプラットフォーム間の違いをマスクし、2)効率的なメモリ割り当てスキームを使用し、3)既存のソースコードに挿入しやすいマクロを作成することです。 以下に、定義の一例を示します。

```
#define A2W(lpa) (\
((LPCSTR)lpa == NULL) NULL : (\
    _convert = (strnlen(lpa)+1),\
    AfxA2WHelper((LPWSTR) alloca(_convert*2),
    lpa,
    _convert)\)\)
```

上記のコードの代わりにこのマクロを使用すると、物事ははるかに簡単です。

```
// use it to call OLE here
USES_CONVERSION;
pI->SomeFunctionThatNeedsUnicode(T2OLE(lpszA));
```

変換が必要な追加の呼び出しがありますが、マクロを使用することは簡単で効果的です。

各マクロの実装では、_alloca() 関数を使用して、ヒープではなくスタックからメモリを割り当てます。 スタックからメモリを割り当てる方がヒープにメモリを割り当てるよりも高速で、関数が終了するとメモリは自動的に解放されます。 また、マクロは複数回呼び`MultiByteToWideChar`出し`WideCharToMultiByte`を回避します。 これは、必要以上に少し多くのメモリを割り当てることによって行われます。 MBC は最大で 1 つの**WCHAR**に変換され、各**WCHAR**に最大 2 MBC バイトが含まれることがわかります。 必要以上に割り当てることによって、変換を処理するのに十分な常に、変換関数への 2 回目の呼び出しは回避されます。 ヘルパー関数`AfxA2Whelper`の呼び出しは、変換を実行するために実行する必要がある引数プッシュの数を減らします (これは、直接呼び出された`MultiByteToWideChar`場合よりも小さいコードになります)。

マクロに一時的な長さを格納するスペースを持たけるためには、変換マクロを使用する各関数で_convertと呼ばれるローカル変数を宣言する必要があります。 これは、上記の例で見たUSES_CONVERSIONマクロを呼び出すことによって行われます。

汎用変換マクロと OLE 固有のマクロの両方があります。 これら 2 つの異なるマクロ セットについて、以下で説明します。 すべてのマクロは AFXPRIV に存在します。H。

## <a name="generic-conversion-macros"></a>汎用変換マクロ

汎用変換マクロは、基礎となるメカニズムを形成します。 前のセクション A2W に示したマクロ例と実装は、そのような「汎用」マクロの 1 つです。 これは、OLE とは特に関係ありません。 汎用マクロのセットは以下のとおりです。

```
A2CW      (LPCSTR) -> (LPCWSTR)
A2W      (LPCSTR) -> (LPWSTR)
W2CA      (LPCWSTR) -> (LPCSTR)
W2A      (LPCWSTR) -> (LPSTR)
```

テキスト変換を行う以外に、変換用のマクロやヘルパー関数`TEXTMETRIC`、 `DEVMODE` `BSTR`、 、 、 OLE 割り当て済み文字列もあります。 これらのマクロは、この説明の範囲を超えています - AFXPRIVを参照してください。これらのマクロの詳細については、H を参照してください。

## <a name="ole-conversion-macros"></a>OLE 変換マクロ

OLE 変換マクロは **、OLESTR**文字を必要とする関数を処理するために特別に設計されています。 OLE ヘッダーを調べてみると **、LPCOLESTR**および**OLECHAR**への参照が多く表示されます。 これらの型は、プラットフォームに固有ではない方法で、OLE インターフェイスで使用される文字の種類を参照するために使用されます。 **OLECHAR**は、Win16 プラットフォームとマッキントッシュ プラットフォームでは**char**にマップされ、Win32 では**WCHAR**にマップされます。

MFC コード内の **#ifdef**ディレクティブの数を最小限に抑えるために、OLE 文字列が関係する変換ごとに同様のマクロを使用します。 最も一般的に使用されるマクロは次のとおりです。

```
T2COLE   (LPCTSTR) -> (LPCOLESTR)
T2OLE   (LPCTSTR) -> (LPOLESTR)
OLE2CT   (LPCOLESTR) -> (LPCTSTR)
OLE2T   (LPCOLESTR) -> (LPCSTR)
```

これも同様に、TEXTMETRIC、DEVMODE、BSTR、および OLE 割り当てストリングを実行するための類似のマクロがあります。 AFXPRIV を参照してください。詳細については H。

## <a name="other-considerations"></a>その他の考慮事項

厳密なループでマクロを使用しないでください。 たとえば、次のようなコードを記述したくない場合があります。

```cpp
void BadIterateCode(LPCTSTR lpsz)
{
    USES_CONVERSION;
    for (int ii = 0; ii <10000; ii++)
    pI->SomeMethod(ii, T2COLE(lpsz));

}
```

上記のコードは、文字列`lpsz`の内容に応じて、スタックにメガバイトのメモリを割り当てることになります! また、ループの反復ごとに文字列を変換するのにも時間がかかります。 代わりに、このような定数変換をループから移動します。

```cpp
void MuchBetterIterateCode(LPCTSTR lpsz)
{
    USES_CONVERSION;
    LPCOLESTR lpszT = T2COLE(lpsz);

    for (int ii = 0; ii <10000; ii++)
    pI->SomeMethod(ii, lpszT);

}
```

文字列が定数でない場合は、メソッド呼び出しを関数にカプセル化します。 これにより、変換バッファは毎回解放されます。 次に例を示します。

```cpp
void CallSomeMethod(int ii, LPCTSTR lpsz)
{
    USES_CONVERSION;
    pI->SomeMethod(ii, T2COLE(lpsz));

}

void MuchBetterIterateCode2(LPCTSTR* lpszArray)
{
    for (int ii = 0; ii <10000; ii++)
    CallSomeMethod(ii, lpszArray[ii]);

}
```

戻り値が戻り値の前にデータのコピーを作成する場合を除き、マクロの結果を返しません。 たとえば、次のコードは不適切です。

```
LPTSTR BadConvert(ISomeInterface* pI)
{
    USES_CONVERSION;
    LPOLESTR lpsz = NULL;
    pI->GetFileName(&lpsz);

LPTSTR lpszT = OLE2T(lpsz);

    CoMemFree(lpsz);

return lpszT; // bad! returning alloca memory
}
```

上記のコードは、戻り値を値をコピーする値に変更することで修正できます。

```
CString BetterConvert(ISomeInterface* pI)
{
    USES_CONVERSION;
    LPOLESTR lpsz = NULL;
    pI->GetFileName(&lpsz);

LPTSTR lpszT = OLE2T(lpsz);

    CoMemFree(lpsz);

return lpszT; // CString makes copy
}
```

マクロは使いやすく、コードに挿入するのは簡単ですが、上記の注意点から分かるように、マクロを使用する際には注意が必要です。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)
