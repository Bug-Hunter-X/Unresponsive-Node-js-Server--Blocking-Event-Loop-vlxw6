# Unresponsive Node.js Server: Blocking Event Loop

This repository demonstrates a common Node.js error where a long-running synchronous operation blocks the event loop, causing the server to become unresponsive.  The `server.js` file shows the problematic code, while `serverSolution.js` provides a solution using asynchronous operations.

## Problem

The original `server.js` uses a `while` loop to simulate a 5-second task.  This synchronous operation blocks the event loop, preventing the server from handling subsequent requests during this time.  Any client trying to connect will experience a delay or timeout.

## Solution

The `serverSolution.js` demonstrates how to refactor the code using asynchronous operations and timers (like `setTimeout`) to avoid blocking the event loop.  This allows the server to remain responsive even during long-running tasks.