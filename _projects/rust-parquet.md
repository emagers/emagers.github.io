---
layout: page
title: "Rust Parquet CLI Tool"
name: rust-parquet
github: https://github.com/emagers/rust-parquet
date: 2021-07-23
---
{% include scripts.html %}

A CLI tool for inspecting Parquet files.

If you've worked with large amounts of data, there's a good chance you've heard of Parquet. Parquet is a columnar data format that is used by many popular data tools and workflows. While very useful, the downside of it is that it isn't easy to inspect the data if you're working with it locally (as in outside of some data warehousing tooling).

In the situation that prompted me to develop this tool, there was actually an alternative available which I did try out: [parquet-cli](https://github.com/chhantyal/parquet-cli). The issue I had with it though was that it was incredibly slow with very large files and I also wanted to be able to output the data in a format that was more useful to me (CSV and JSON).

The obvious choice to improve the performance was to write it in Rust. This was a little difficult because the Rust parquet library support and documentation was not great, and I'm sure by now the APIs have improved significantly or there are easier wrappers out there.

Overall, it did significantly improve the performance for what I was trying to do, and being able to get samples of the data in formats I could then use in testing data engineering workflows was a huge plus.

Find out how you can use [rust-parquet]({{ page.github }}) here and let me know what you think!