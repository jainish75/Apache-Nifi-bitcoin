# Apache NiFi: Bitcoin Historical Data Ingestion and Analysis

## Project Overview
This project demonstrates the use of Apache NiFi, an open-source data integration and automation platform, to extract historical Bitcoin price data from a public API, transform the data into a structured JSON format, and persist it in a local directory as individual JSON files.

## Prerequisites
- Apache NiFi (version 1.x or later)
- Access to the Bitcoin Price API (https://api.blockchain.info/charts/market-price)

## NiFi Flow Design
The NiFi flow consists of the following components:

1. **InvokeHTTP Processor**: Retrieves historical Bitcoin price data from the specified API.
2. **JoltTransformJSON Processor**: The retrieved data from the Bitcoin price API was in JSON format, and the SplitJson processor was employed to transform and restructure this JSON data into the desired format
3. **PutFile Processor**: Writes the transformed JSON data to a local directory as individual JSON files.

## Usage
1. Import the NiFi flow template (`bitcoin-price-ingestion.xml`) into your Apache NiFi instance.
2. Configure the `InvokeHTTP Processor` with the appropriate API endpoint URL.
3. Adjust the `PutFile Processor` to specify the desired local directory for storing the JSON files.
4. Start the NiFi flow.
5. Monitor the flow execution and verify the successful extraction, transformation, and persistence of the Bitcoin price data.

## Results
Upon successful execution, the NiFi flow will:

1. Extract historical Bitcoin price data from the specified API.
2. Transform the retrieved data into a structured JSON format, including fields for date, opening price, high price, and low price.
3. Persist the transformed data in the specified local directory as individual JSON files, with each file representing a single data point.

## Troubleshooting
- Ensure that the API endpoint URL is correct and accessible.
- Check the NiFi logs for any error messages or warnings.
- Verify the file permissions and available disk space for the local directory specified in the `PutFile Processor`.

## References
- Apache NiFi Project: https://nifi.apache.org/
- NiFi User Guide: https://nifi.apache.org/docs/nifi-docs/html/user-guide.html
- Bitcoin Price API: https://api.blockchain.info/charts/market-price
