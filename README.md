# 【今日から始めるプログラミング】自作プログラミング言語から始めるTypeScript入門
> 前置記法の小さな言語を、TypeScriptで「Compiler / Runtime」から作って、CLIとWebまで完成させるWeb book

このリポジトリは、**プログラミング初心者**が
「自作の小さな言語を作って動かす」体験を通して、プログラミングの基本とTypeScriptを学べるWeb bookです。

## この本で作るもの
- 前置記法の自作言語（式・関数・変数）
- Compiler（パース→AST→変換/生成）
- Runtime（VM）
- Node.js で動く CLI ツール
- ブラウザで動く Web エディタ

## 言語の例（案）

初心者向けなので、真理値と数値と数値の配列と定数文字列しか扱いません  
定義の巻き上げも行いません  
C言語のような感じで頭で宣言します  

```ts
function sum3 (a: number,b: number,c: number): number; // 先行宣言

function main (): void {
    let a = add 1 2;
    let b = sum3 a 3 4;
    log "result:";
    log b;
    if (eq b 10) {
        log "OK";
    }
    else {
        log "Err";
    }
}
function sum3 (a: number,b: number,c: number): number {
    return add add a b c;
}
```

## コンパイラ

出力を確認しやすいよう、アセンブリ相当のものとして、JSONファイルを出力します

## VM

簡単なスタックマシンのランタイムを作成します
コンパイラが出力するJSONを読み込んで実行します

## 想定読者

* プログラミングを始めたばかりで、基礎から体系的に理解したい人
* TypeScriptを「文法だけ」ではなく「作って動かす」で学びたい人
* CLI / Web の両方の入り口を掴みたい人

## 学べること

* 解析と変換の基本：tokenize / parse / AST / evaluate
* TypeScriptの基礎：型、関数、スコープ、例外、モジュール
* CLIアプリの基礎：引数、標準入力、ファイルI/O、配布
* Webアプリの基礎：UI、イベント、ブラウザ上での実行

## リポジトリ構成（案）

* src/
  * lang-core/        : AST, tokenizer, parser（共通）
  * lang-compiler/    : 変換/生成（JSON生成）
  * lang-runtime/     : evaluator/VM
  * lang-cli/         : Node.js CLI（実行・REPL・ビルド）
  * lang-web/         : Web UI（ブラウザ実行デモ,テキストエディタ）